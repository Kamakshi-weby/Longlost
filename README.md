<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Plant Problem Diagnoser</title>
  <style>
    :root{--bg:#0f1724;--card:#111827;--muted:#9ca3af;--accent:#7c3aed}
    *{box-sizing:border-box;font-family:Inter,ui-sans-serif,system-ui,Segoe UI,Roboto,"Helvetica Neue",Arial}
    body{margin:0;background:linear-gradient(180deg,#071025 0%,#0b1220 100%);color:#e6eef8;padding:22px;min-height:100vh}
    .wrap{max-width:980px;margin:0 auto}
    h1{font-size:1.9rem;margin:0 0 10px;text-decoration:underline}
    p.lead{color:var(--muted);margin-top:6px}
    .grid{display:grid;gap:16px;grid-template-columns:1fr}
    @media(min-width:900px){.grid{grid-template-columns:420px 1fr}}
    .card{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); padding:16px;border-radius:14px;box-shadow:0 6px 18px rgba(2,6,23,0.6);border:1px solid rgba(255,255,255,0.03)}
    label{display:block;font-weight:600;margin-bottom:6px}
    input[type=file], textarea{width:100%;padding:10px;border-radius:8px;border:1px solid rgba(255,255,255,0.06);background:transparent;color:inherit}
    button{background:var(--accent);border:none;color:white;padding:10px 14px;border-radius:10px;cursor:pointer;font-weight:600}
    button.ghost{background:transparent;border:1px solid rgba(255,255,255,0.06)}
    .flex{display:flex;gap:8px;align-items:center}
    .preview{width:100%;height:260px;background:#0b1220;border-radius:8px;display:flex;align-items:center;justify-content:center;overflow:hidden}
    .preview img{max-width:100%;max-height:100%;object-fit:contain}
    .results{margin-top:12px}
    .chip{display:inline-block;background:rgba(255,255,255,0.03);padding:8px;border-radius:999px;margin-right:8px;margin-bottom:8px;font-size:0.9rem}
    .note{color:var(--muted);font-size:0.9rem;margin-top:8px}
    pre{white-space:pre-wrap;word-break:break-word;background:rgba(255,255,255,0.01);padding:12px;border-radius:8px;border:1px dashed rgba(255,255,255,0.03);color:var(--muted)}
    footer{margin-top:18px;color:var(--muted);font-size:0.9rem}
  </style>
</head>
<body>
  <div class="wrap">
    <h1>Plant Problem Diagnoser</h1>
    <p class="lead">Upload a leaf photo or use your camera. The tool runs fully in-browser and uses simple image heuristics + a symptom textbox to suggest likely issues.</p>

    <div class="grid">
      <!-- LEFT: image + capture -->
      <div class="card">
        <label>Take photo or upload</label>
        <div class="flex" style="margin-bottom:10px">
          <input id="file" type="file" accept="image/*" />
          <button id="cameraBtn" class="ghost">Use Camera</button>
          <button id="clearBtn" class="ghost">Clear</button>
        </div>

        <div class="preview" id="preview">No image yet</div>

        <div style="display:flex;gap:8px;margin-top:10px">
          <button id="analyzeBtn">Analyze Image</button>
          <button id="downloadBtn" class="ghost">Download Processed</button>
        </div>

        <div class="note">Tip: take a close clear photo of the affected leaf (top & underside if possible). Avoid heavy backlight.</div>
      </div>

      <!-- RIGHT: symptoms + results -->
      <div>
        <div class="card">
          <label>Describe symptoms (optional)</label>
          <textarea id="symptoms" rows="5" placeholder='e.g. "Older leaves yellowing, small brown spots on upper surface, leaf edges burnt"'></textarea>
          <div style="margin-top:8px" class="flex">
            <button id="analyzeText">Analyze Symptoms</button>
            <button id="combine" class="ghost">Use both</button>
          </div>

          <div class="results" id="results">
            <h3 style="margin:12px 0 6px">Results</h3>
            <div id="badges"></div>
            <div id="advice"></div>
          </div>
        </div>

        <div class="card" style="margin-top:12px">
          <h4 style="margin:0 0 8px">Debug / Raw metrics</h4>
          <pre id="metrics">No image processed yet.</pre>
          <div class="note">This shows percentages we measured (yellowing, browning, green area, spot density).</div>
        </div>
      </div>
    </div>

    <footer>
      <div>Privacy: runs entirely in your browser — no images are uploaded anywhere.</div>
      <div style="margin-top:6px">Limitations: heuristic-only. For production-grade identification use a trained model or a plant-ID API behind a server.</div>
    </footer>
  </div>

  <!-- hidden canvas to process image -->
  <canvas id="cv" style="display:none"></canvas>

<script>
/* Single-file client-side diagnoser
   - Heuristics:
     * Detect % green, % yellow, %brown based on HSV thresholds
     * Detect spot density by finding small clusters of brown/dark pixels
   - Use these metrics + symptom-text keyword matches to suggest likely issues
*/

const fileEl = document.getElementById('file');
const preview = document.getElementById('preview');
const cv = document.getElementById('cv');
const analyzeBtn = document.getElementById('analyzeBtn');
const analyzeTextBtn = document.getElementById('analyzeText');
const clearBtn = document.getElementById('clearBtn');
const cameraBtn = document.getElementById('cameraBtn');
const metricsPre = document.getElementById('metrics');
const badges = document.getElementById('badges');
const advice = document.getElementById('advice');
const symptomsEl = document.getElementById('symptoms');
const downloadBtn = document.getElementById('downloadBtn');
const combineBtn = document.getElementById('combine');

let img = null;
let stream = null;

// helpers: RGB -> HSV
function rgbToHsv(r,g,b){
  r/=255; g/=255; b/=255;
  const max=Math.max(r,g,b), min=Math.min(r,g,b);
  let h=0,s=0,v=max;
  const d=max-min;
  s = max===0 ? 0 : d/max;
  if(max===min) h=0;
  else {
    switch(max){
      case r: h = (g-b)/d + (g<b?6:0); break;
      case g: h = (b-r)/d + 2; break;
      case b: h = (r-g)/d + 4; break;
    }
    h/=6;
  }
  return [h*360, s*100, v*100];
}

function showPreviewImage(fileOrUrl){
  if(typeof fileOrUrl === 'string'){
    preview.innerHTML = '<img src="'+fileOrUrl+'" id="previewImg">';
  } else {
    const url = URL.createObjectURL(fileOrUrl);
    preview.innerHTML = '<img src="'+url+'" id="previewImg">';
  }
  img = document.getElementById('previewImg');
}

// file input
fileEl.addEventListener('change', e=>{
  const f = e.target.files && e.target.files[0];
  if(!f) return;
  stopCamera();
  showPreviewImage(f);
});

// camera
cameraBtn.addEventListener('click', async ()=>{
  if(stream){ stopCamera(); return; }
  try {
    stream = await navigator.mediaDevices.getUserMedia({video:{facingMode:'environment'}, audio:false});
    const v = document.createElement('video');
    v.autoplay = true;
    v.playsInline = true;
    v.srcObject = stream;
    v.style.width = '100%'; v.style.height = '100%';
    preview.innerHTML = '';
    preview.appendChild(v);

    // take shot on click
    preview.addEventListener('click', function takeShot(){
      const canvas = document.createElement('canvas');
      canvas.width = v.videoWidth; canvas.height = v.videoHeight;
      canvas.getContext('2d').drawImage(v,0,0);
      const url = canvas.toDataURL('image/jpeg');
      stopCamera();
      showPreviewImage(url);
      preview.removeEventListener('click', takeShot);
    }, {once:true});

  } catch(err){
    alert('Camera access denied or unavailable.');
  }
});

function stopCamera(){
  if(!stream) return;
  stream.getTracks().forEach(t=>t.stop());
  stream=null;
  // hide video if present
  const vid = preview.querySelector('video');
  if(vid) vid.remove();
  if(!img) preview.textContent = 'No image yet';
}

// clear
clearBtn.addEventListener('click', ()=>{
  fileEl.value='';
  preview.innerHTML='No image yet';
  img=null;
  badges.innerHTML='';
  advice.innerHTML='';
  metricsPre.textContent='No image processed yet.';
});

// combine button: runs both
combineBtn.addEventListener('click', async ()=>{
  await runAnalysis(true);
});

// analyze text only
analyzeTextBtn.addEventListener('click', ()=>{
  const s = symptomsEl.value || '';
  const tres = analyzeSymptomsText(s);
  renderResults(tres);
});

// analyze image
analyzeBtn.addEventListener('click', async ()=>{
  await runAnalysis(false);
});

// download processed image (canvas)
downloadBtn.addEventListener('click', ()=>{
  const cvEl = document.getElementById('cv');
  if(!cvEl.width){ alert('Process an image first.'); return;}
  const url = cvEl.toDataURL('image/png');
  const a = document.createElement('a');
  a.href = url; a.download='processed.png'; a.click();
});

async function runAnalysis(useSymptomsAlso=false){
  badges.innerHTML=''; advice.innerHTML='';
  if(!img){ alert('Upload or capture an image first.'); return; }
  // wait for image to load if it's a URL
  if(!img.complete){ await new Promise(res=>img.onload=res); }

  // draw to canvas with max size
  const maxW=1200, maxH=800;
  let w = img.naturalWidth || img.width, h = img.naturalHeight || img.height;
  const scale = Math.min(1, maxW/w, maxH/h);
  w = Math.round(w*scale); h = Math.round(h*scale);
  cv.width = w; cv.height = h;
  const ctx = cv.getContext('2d');
  ctx.drawImage(img, 0, 0, w, h);

  // basic auto-crop to leaf-like area (center crop heuristic)
  // We'll analyze the whole image but ignore transparent pixels (if any)
  const imd = ctx.getImageData(0,0,w,h);
  const data = imd.data;

  // compute metrics
  let total=0, greenCount=0, yellowCount=0, brownCount=0, darkCount=0, brightCount=0;
  // spot detection: count isolated brown/dark pixels
  let brownSpots=0;

  for(let i=0;i<data.length;i+=4){
    const r=data[i], g=data[i+1], b=data[i+2], a=data[i+3];
    if(a===0) continue;
    total++;
    const [hue,sat,val] = rgbToHsv(r,g,b);
    // determine categories by HSV heuristics
    // green: hue ~60-160, sat>20, val>15
    if(hue>=60 && hue<=160 && sat>20 && val>10) greenCount++;
    // yellow: hue ~30-60 and sat>15
    if(hue>=22 && hue<=65 && sat>15 && val>25) yellowCount++;
    // brown: low brightness + redish/orange hue OR low sat + med val
    if( ( (hue>=10 && hue<=45) && val<50 && sat>10 ) || (sat<35 && val<40) ) { brownCount++; }
    if(val < 25) darkCount++;
    if(val > 85) brightCount++;
  }

  // spot density: coarse method - look for small clusters of brownish pixels
  function isBrownAt(i){
    const r=data[i], g=data[i+1], b=data[i+2];
    const [hue,sat,val] = rgbToHsv(r,g,b);
    return ( (hue>=10 && hue<=45 && val<60 && sat>12) || (sat<35 && val<45) );
  }
  // scan grid cells
  const step = Math.max(2, Math.round(Math.min(w,h)/150)); // speed vs detail
  let spotPixels=0, spotClusters=0;
  for(let y=2; y<h-2; y+=step){
    for(let x=2; x<w-2; x+=step){
      const idx = (y*w + x)*4;
      if(isBrownAt(idx)){
        spotPixels++;
        // check neighborhood for cluster
        let cluster=0;
        for(let yy=-2; yy<=2; yy+=step){
          for(let xx=-2; xx<=2; xx+=step){
            const ni = ((y+yy)*w + (x+xx))*4;
            if(ni>=0 && ni<data.length && isBrownAt(ni)) cluster++;
          }
        }
        if(cluster>2) spotClusters++;
      }
    }
  }
  // clamp
  const greenPct = Math.round(greenCount/total*100);
  const yellowPct = Math.round(yellowCount/total*100);
  const brownPct = Math.round(brownCount/total*100);
  const darkPct = Math.round(darkCount/total*100);
  const spotDensity = Math.round(spotClusters / Math.max(1, (w*h)/(10000)) * 100);

  // draw overlay: highlight brown spots in red and yellow zones in yellow (for download)
  // create overlay copy
  const overlay = ctx.getImageData(0,0,w,h);
  for(let y=0;y<h;y+=2){
    for(let x=0;x<w;x+=2){
      const i = (y*w + x)*4;
      const [hue,sat,val] = rgbToHsv(data[i],data[i+1],data[i+2]);
      if( (hue>=22 && hue<=65 && sat>15 && val>25) ){ // yellow
        overlay.data[i] = Math.min(255, overlay.data[i]+30);
        overlay.data[i+1] = Math.min(255, overlay.data[i+1]+30);
        overlay.data[i+2] = Math.max(0, overlay.data[i+2]-30);
      }
      if(isBrownAt(i)){ // brown -> tint red
        overlay.data[i] = Math.min(255, overlay.data[i]+80);
        overlay.data[i+1] = Math.max(0, overlay.data[i+1]-40);
        overlay.data[i+2] = Math.max(0, overlay.data[i+2]-40);
      }
    }
  }
  ctx.putImageData(overlay,0,0);
  // replace preview image with processed canvas
  const dataUrl = cv.toDataURL('image/png');
  preview.innerHTML = '<img src="'+dataUrl+'" style="max-width:100%;height:100%;object-fit:contain">';
  img = preview.querySelector('img');

  // prepare textual diagnosis heuristics
  const textual = [];
  // yellowing widespread -> nitrogen deficiency likely
  if(yellowPct > 18 && greenPct < 60){
    textual.push({name:'Widespread yellowing', reason:`${yellowPct}% yellow pixels detected`, advice:'Possible nitrogen deficiency or general chlorosis. Apply balanced N-rich feed, check watering and soil fertility.'});
  }
  // high yellow but veins remain darker: we can't detect veins reliably; warn user
  if(yellowPct > 8 && greenPct > 30 && yellowPct/Math.max(1,greenPct) > 0.5){
    textual.push({name:'Interveinal yellowing likely', reason:`Yellow: ${yellowPct}%, Green: ${greenPct}%`, advice:'Interveinal chlorosis (could be iron or magnesium deficiency). Check soil pH, consider foliar iron chelate.'});
  }
  // brown spots -> disease or sun/fertilizer burn
  if(brownPct > 6 || spotDensity > 6){
    textual.push({name:'Brown spots / necrosis', reason:`Brown ${brownPct}%, spot density ${spotDensity}`, advice:'Could be fungal/bacterial disease, pest damage, or localized necrosis (salt burn). Remove affected leaves, improve airflow, avoid overhead watering. Consider fungicide if fungal.'});
  }
  // dark leaves and low green -> overwatering/rot or poor root uptake
  if(darkPct > 20 && greenPct < 30){
    textual.push({name:'Dark, dull leaves', reason:`Dark pixels ${darkPct}%`, advice:'Possible overwatering or root issues (root-rot) — check roots and soil moisture.'});
  }
  // mostly green & small brown spots -> pests
  if(greenPct > 50 && spotDensity > 4 && brownPct>2){
    textual.push({name:'Healthy foliage with localized spots', reason:'Spots present on mostly green plant', advice:'Look for pests (thrips, mites) or early disease. Inspect underside of leaves.'});
  }
  // if nothing strong
  if(textual.length===0){
    textual.push({name:'Unclear from image', reason:`Green ${greenPct}%, Yellow ${yellowPct}%, Brown ${brownPct}%`, advice:'Try another photo showing top and underside of affected leaves, or add details in the symptom box.'});
  }

  // include symptom-text suggestions if requested
  let textSuggestions = [];
  if(useSymptomsAlso || symptomsEl.value.trim().length>0){
    textSuggestions = analyzeSymptomsText(symptomsEl.value || '');
  }

  // merge & render
  const combined = mergeSuggestions(textual, textSuggestions);
  renderResults(combined);

  // metrics
  metricsPre.textContent = `Green: ${greenPct}%\nYellow: ${yellowPct}%\nBrown: ${brownPct}%\nDark: ${darkPct}%\nSpot clusters (coarse): ${spotClusters}\nSpot density index: ${spotDensity}`;
}

// symptom text analyzer (keyword-based)
function analyzeSymptomsText(text){
  const t = (text||'').toLowerCase();
  const out = [];
  if(!t || t.trim().length===0) return out;
  if(/older leaves.*yellow|older leaves turning yellow|lower leaves yellow/.test(t) || /nitrogen/.test(t)) {
    out.push({name:'Nitrogen deficiency', reason:'Yellowing of older leaves', advice:'Apply nitrogen-rich fertilizer; compost or balanced NPK.'});
  }
  if(/interveinal|between veins|veins remain green|veins green/.test(t) || /iron/.test(t)){
    out.push({name:'Iron / micronutrient deficiency (interveinal chlorosis)', reason:'Yellowing between veins', advice:'Check soil pH and use iron chelate foliar spray.'});
  }
  if(/brown edges|edges brown|leaf edges brown|scorched edges/.test(t) || /fertilizer burn|salt burn/.test(t)){
    out.push({name:'Fertilizer/salt burn or drought stress', reason:'Brown/necrotic edges', advice:'Flush soil, reduce fertilizer, water evenly.'});
  }
  if(/spots|brown spots|necrotic spots|rust|blight|powdery/.test(t) || /fungal|bacterial/.test(t)){
    out.push({name:'Fungal or bacterial disease possible', reason:'Spots described', advice:'Remove infected tissue, improve airflow, consider fungicide if needed.'});
  }
  if(/curl|droop|wilting|wilted/.test(t) || /root rot|overwater/.test(t)){
    out.push({name:'Water stress / root problem', reason:'Wilting or root rot described', advice:'Check soil moisture, repot if root rot suspected, adjust watering.'});
  }
  if(out.length===0) out.push({name:'No strong match from text', reason:'Text had no known keywords', advice:'Add more detail (which leaves, pattern, progression).'});
  return out;
}

function mergeSuggestions(imgSug, textSug){
  // naive merge: put text suggestions first then unique image suggestions
  const out = [];
  const seen = new Set();
  textSug.forEach(s=>{ out.push(s); seen.add(s.name); });
  imgSug.forEach(s=>{ if(!seen.has(s.name)) out.push(s); });
  return out;
}

function renderResults(list){
  badges.innerHTML=''; advice.innerHTML='';
  list.forEach(item=>{
    const chip = document.createElement('div');
    chip.className='chip';
    chip.textContent = item.name;
    badges.appendChild(chip);

    const block = document.createElement('div');
    block.style.marginTop='8px';
    block.innerHTML = `<strong>${item.name}</strong><div style="color:var(--muted);margin-top:6px">${item.reason || ''}</div><div style="margin-top:8px">${item.advice || ''}</div>`;
    advice.appendChild(block);
  });
}

// small convenience to stop camera on unload
window.addEventListener('beforeunload', ()=>{ stopCamera(); });
</script>
</body>
</html>

