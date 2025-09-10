    
import React, { useState } from "react";

// Plant Deficiency Diagnoser - Single-file React component
// Tailwind CSS classes used for layout and styling (no external CSS required here,
// but the parent project should include Tailwind). This component is a starting
// point: it performs symptom-based rule matching locally and can optionally
// call the Plant.id API for image-based identification.

// ====== CONFIG ======
// If you have a Plant.id API key, paste it here. If empty, the app will only use
// the local symptom matcher. To get an API key: https://plant.id (or any other
// plant-identification service). Remember: do NOT commit secret keys to public
// repos. For production, proxy this key via a server.
const PLANT_ID_API_KEY = ""; // <-- Paste your Plant.id API key here (or leave blank)

export default function PlantDiagnoser() {
  const [imageFile, setImageFile] = useState(null);
  const [previewUrl, setPreviewUrl] = useState("");
  const [symptomsText, setSymptomsText] = useState("");
  const [loading, setLoading] = useState(false);
  const [results, setResults] = useState(null);
  const [error, setError] = useState("");

  // Local symptom-rule engine: simple keyword matching. This is intentionally
  // conservative and meant as a fallback/demo. Expand rules as you test with real plants.
  function symptomRuleMatch(text) {
    const t = text.toLowerCase();
    const matches = [];

    if (!t || t.trim().length === 0) return matches;

    if (/(yellow|chlorosis|pale).*(between|between veins|veins)/.test(t) || /interveinal yellow/.test(t)) {
      matches.push({
        name: "Iron deficiency (interveinal chlorosis)",
        confidence: 0.6,
        advice: "Check soil pH (often too high), consider iron chelate foliar spray or correct pH."
      });
    }

    if (/(overall yellow|pale leaves|yellow leaves).*(older leaves|older)/.test(t) || /(nitrogen|nitrogen deficiency)/.test(t)) {
      matches.push({
        name: "Nitrogen deficiency",
        confidence: 0.7,
        advice: "Apply a balanced nitrogen-rich fertilizer; older leaves yellow first."
      });
    }

    if (/(brown edges|leaf edges brown|scorched edges)/.test(t) || /(salt burn|too much fertilizer)/.test(t)) {
      matches.push({
        name: "Salt / fertilizer burn or drought stress",
        confidence: 0.65,
        advice: "Flush soil with water, check recent fertilization; reduce fertilizer and ensure even watering."
      });
    }

    if (/(brown spots|necrotic spots|spots on leaves)/.test(t) || /(fungal|blight|rust|powdery mildew)/.test(t)) {
      matches.push({
        name: "Possible fungal or bacterial disease",
        confidence: 0.7,
        advice: "Remove affected leaves, improve air circulation, consider fungicide if necessary. Identify exact pathogen for targeted treatment."
      });
    }

    if (/(curl|droop|wilting|wilted)/.test(t) || /(root rot|overwater)/.test(t)) {
      matches.push({
        name: "Water stress or root problem (root rot/underwatering)",
        confidence: 0.7,
        advice: "Check soil moisture, roots; reduce overwatering or water more consistently. Repot if root rot suspected."
      });
    }

    if (/(purple stems|reddish leaves|phosphorus)/.test(t)) {
      matches.push({
        name: "Possible phosphorus deficiency",
        confidence: 0.5,
        advice: "Use a fertilizer with phosphorus and check soil temperature (cold soils limit uptake)."
      });
    }

    if (matches.length === 0) {
      matches.push({
        name: "Not sure from text",
        confidence: 0.2,
        advice: "Try uploading a clear photo (top-side and underside of leaves) or add more symptom details (age of affected leaves, pattern, progression)."
      });
    }

    return matches;
  }

  async function analyzeBySymptoms() {
    setError("");
    setResults(null);
    setLoading(true);
    try {
      const local = symptomRuleMatch(symptomsText);
      setResults({source: "symptom-text", diagnoses: local});
    } catch (e) {
      setError(String(e));
    } finally {
      setLoading(false);
    }
  }

  async function analyzeImage() {
    setError("");
    setResults(null);
    if (!imageFile) {
      setError("Please upload an image first.");
      return;
    }

    setLoading(true);
    try {
      if (!PLANT_ID_API_KEY) {
        // No API key: return a friendly message and show local heuristic
        setResults({
          source: "local-fallback",
          diagnoses: [
            {
              name: "No image analysis (no API key)",
              confidence: 0.1,
              advice:
                "You can paste a Plant.id (or other) API key at the top of the component to enable cloud image analysis. Meanwhile, try the text-symptom analyser."
            }
          ]
        });
        setLoading(false);
        return;
      }

      // Example call to Plant.id v2 detect endpoint. Production: proxy the key via a backend.
      // For usage details see: https://web.plant.id/api-docs (API changes over time; check docs)

      const form = new FormData();
      form.append("api_key", PLANT_ID_API_KEY);
      form.append("organs", JSON.stringify(["leaf"]));
      form.append("images", imageFile);

      const resp = await fetch("https://api.plant.id/v2/identify", {
        method: "POST",
        body: form
      });

      if (!resp.ok) {
        const txt = await resp.text();
        throw new Error(`Plant.id API error: ${resp.status} ${txt}`);
      }

      const data = await resp.json();

      // Plant.id returns suggestions; we lightly convert them for display. Structure
      // may change depending on API version.
      const diagnoses = (data?.suggestions || []).map((s) => ({
        name: s?.plant?.common_names?.[0] || s?.plant?.scientific_name || s?.plant_name || s?.name || "Unknown",
        confidence: s?.probability ?? s?.score ?? 0,
        details: s
      }));

      if (diagnoses.length === 0) {
        diagnoses.push({name: "No confident identification", confidence: 0});
      }

      setResults({source: "plant.id", raw: data, diagnoses});
    } catch (e) {
      setError(String(e));
    } finally {
      setLoading(false);
    }
  }

  function onFileChange(e) {
    const f = e.target.files?.[0];
    if (!f) return;
    setImageFile(f);
    const url = URL.createObjectURL(f);
    setPreviewUrl(url);
  }

  return (
    <div className="min-h-screen bg-gradient-to-b from-gray-900 to-gray-800 text-gray-100 p-6">
      <div className="max-w-4xl mx-auto">
        <h1 className="text-3xl font-extrabold underline mb-4">Plant Deficiency Diagnoser</h1>
        <p className="mb-4 opacity-80">Upload a clear leaf photo or describe the symptoms and get likely causes and advice.</p>

        <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
          <div className="p-4 bg-gray-900/40 rounded-2xl shadow-lg">
            <h2 className="text-xl font-semibold underline mb-2">1) Image-based analysis</h2>
            <input onChange={onFileChange} accept="image/*" type="file" className="mb-3" />
            {previewUrl && (
              <img src={previewUrl} alt="preview" className="w-full h-48 object-contain rounded-md mb-3" />
            )}
            <div className="flex gap-2">
              <button onClick={analyzeImage} className="px-4 py-2 rounded-xl bg-green-600/90 hover:bg-green-600">Analyze Image</button>
              <button
                onClick={() => {
                  setImageFile(null);
                  setPreviewUrl("");
                }}
                className="px-4 py-2 rounded-xl bg-gray-700/80"
              >
                Clear
              </button>
            </div>
            <p className="mt-3 text-sm opacity-80">Note: For automated image results you must provide a Plant.id API key in the source code or run a backend proxy. Otherwise the app will use a local fallback.</p>
          </div>

          <div className="p-4 bg-gray-900/40 rounded-2xl shadow-lg">
            <h2 className="text-xl font-semibold underline mb-2">2) Symptom text analysis</h2>
            <textarea
              rows={8}
              value={symptomsText}
              onChange={(e) => setSymptomsText(e.target.value)}
              placeholder={`Example: "Older leaves turning yellow, veins remain green, small brown spots appear"`}
              className="w-full p-3 rounded-xl bg-gray-800/60"
            />
            <div className="flex gap-2 mt-3">
              <button onClick={analyzeBySymptoms} className="px-4 py-2 rounded-xl bg-indigo-600/90 hover:bg-indigo-600">Analyze Symptoms</button>
              <button
                onClick={() => setSymptomsText("")}
                className="px-4 py-2 rounded-xl bg-gray-700/80"
              >
                Clear
              </button>
            </div>
            <p className="mt-3 text-sm opacity-80">The text analyser is a lightweight keyword matcher — good for quick hints but not a replacement for lab or expert diagnosis.</p>
          </div>
        </div>

        <div className="mt-6 p-4 bg-gray-900/40 rounded-2xl shadow-lg">
          <h2 className="text-2xl font-semibold underline mb-3">Results</h2>

          {loading && <div className="italic">Analysing…</div>}

          {error && <div className="text-red-400 mb-3">Error: {error}</div>}

          {results && (
            <div>
              <div className="mb-2 text-sm opacity-80">Source: {results.source}</div>
              <div className="grid gap-3">
                {results.diagnoses.map((d, i) => (
                  <div key={i} className="p-3 bg-gray-800/60 rounded-xl border border-gray-700">
                    <div className="flex items-baseline justify-between">
                      <div className="font-semibold text-lg">{d.name}</div>
                      <div className="text-sm opacity-80">Confidence: {(d.confidence ?? 0).toFixed(2)}</div>
                    </div>
                    {d.advice && <div className="mt-2">{d.advice}</div>}
                    {d.details && (
                      <details className="mt-2 text-sm opacity-80">
                        <summary>Raw details</summary>
                        <pre className="whitespace-pre-wrap text-xs">{JSON.stringify(d.details, null, 2)}</pre>
                      </details>
                    )}
                  </div>
                ))}
              </div>
            </div>
          )}

          {!results && !loading && <div className="opacity-70">No results yet — try uploading an image or entering symptoms above.</div>}
        </div>

        <div className="mt-6 text-sm opacity-80">
          <h3 className="font-semibold">Next steps & improvements</h3>
          <ul className="list-disc ml-5">
            <li>Add a small Node/Express backend to keep your Plant.id API key secret.</li>
            <li>Train or fine-tune a TensorFlow / Hugging Face model for offline image inference and bundle it with TensorFlow.js.</li>
            <li>Increase the symptom-rule database and add image pre-processing (crop, focus on leaf) for better accuracy.</li>
            <li>Collect labeled examples to improve your model and to measure accuracy per plant species.</li>
          </ul>
        </div>

      </div>
    </div>
  );
}
