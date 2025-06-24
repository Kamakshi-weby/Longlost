<!DOCTYPE html>
<html lang="en">
<head>  
  <meta charset="UTF-8">  
  <meta name="viewport" content="width=device-width, initial-scale=1.0">  
  <title>Playful Blog</title>  
  <style>  
    body {  
      margin: 0;  
      font-family: 'Comic Sans MS', cursive, sans-serif;  
      background-color: lavender;  
      color: #333;  
    }  
    header, footer {  
      background-color: #ffb347;  
      text-align: center;  
      padding: 1em;  
    }  
    nav {  
      background-color: #ffcc80;  
      padding: 0.5em;  
      text-align: center;  
    }  
    nav a {  
      margin: 0 1em;  
      color: #444;  
      text-decoration: none;  
      font-weight: bold;  
    }  
    section {  
      padding: 2em;  
    }  
    .blog-entry {  
      background: #fff8dc;  
      border-radius: 10px;  
      padding: 1em;  
      margin: 1em 0;  
      box-shadow: 0 0 10px rgba(0,0,0,0.1);  
    }  
    .game-section {  
      margin-top: 2em;  
      padding: 1em;  
      background-color: #ffe0b2;  
      border-radius: 12px;  
    }  
    .game-section h3 {  
      color: #d84315;  
    }  
    .game-board, .memory-grid, .rps-buttons {  
      margin-top: 1em;  
    }  
    .cell {  
      width: 60px;  
      height: 60px;  
      border: 2px solid #333;  
      display: inline-block;  
      text-align: center;  
      line-height: 60px;  
      font-size: 24px;  
      cursor: pointer;  
    }  
    .memory-card {  
      width: 60px;  
      height: 60px;  
      display: inline-block;  
      background-color: #fff;  
      border: 2px solid #333;  
      margin: 5px;  
      text-align: center;  
      line-height: 60px;  
      font-size: 24px;  
      cursor: pointer;  
    }  
    h1, h2, h3 {  
      position: relative;  
      display: inline-block;  
      padding-bottom: 0.3em;  
      margin-bottom: 0.5em;  
      font-weight: bold;  
      text-align: center;  
      color: #6a1b9a; /* Deep lavender color */  
    }  
    
    h1::after, h2::after, h3::after {  
      content: '';  
      position: absolute;  
      width: 60%;  
      height: 4px;  
      background-color: #ff69b4; /* Pink underline */  
      left: 20%;  
      bottom: 0;  
      border-radius: 2px;  
    }  
    
    #myself {  
      background: linear-gradient(135deg, #ffe6f7, #d1c4e9);  
      border-radius: 16px;  
      padding: 2em;  
      box-shadow: 0 0 15px rgba(0,0,0,0.2);  
      animation: popUp 0.7s ease-out;  
      transition: transform 0.3s;  
    }  
    
    #myself:hover {  
      transform: scale(1.02);  
    }  
    
    @keyframes popUp {  
      from {  
        opacity: 0;  
        transform: scale(0.95);  
      }  
      to {  
        opacity: 1;  
        transform: scale(1);  
      }  
    }  
    
    #myself h2 {  
      color: #8e24aa;  
    }  
    
    #myself p {  
      color: #4a148c;  
      font-size: 1.05em;  
      line-height: 1.6;  
    }  
    #about {  
      background: linear-gradient(135deg, #e0f7fa, #b2ebf2); /* Soft cyan shades */  
      border-radius: 16px;  
      padding: 2em;  
      box-shadow: 0 0 15px rgba(0, 0, 0, 0.15);  
      animation: fadeIn 0.7s ease-out;  
      transition: transform 0.3s;  
    }  
    
    #about:hover {  
      transform: scale(1.02);  
    }  
    
    #about h2 {  
      color: #00796b; /* Teal green */  
    }  
    
    #about p {  
      color: #004d40;  
      font-size: 1.05em;  
      line-height: 1.6;  
    }  
    
    @keyframes fadeIn {  
      from {  
        opacity: 0;  
        transform: translateY(10px);  
      }  
      to {  
        opacity: 1;  
        transform: translateY(0);  
      }  
    }  
    #home {  
      background: linear-gradient(135deg, #ffe082, #ffca28); /* Warm yellow-orange gradient */  
      border-radius: 16px;  
      padding: 2em;  
      box-shadow: 0 0 20px rgba(255, 193, 7, 0.3);  
      animation: bounceIn 0.7s ease-out;  
      transition: transform 0.3s;  
    }  
    
    #home:hover {  
      transform: scale(1.02);  
    }  
    
    #home h2 {  
      color: #bf360c; /* Deep warm orange */  
    }  
    
    #home p {  
      color: #4e342e;  
      font-size: 1.05em;  
      line-height: 1.6;  
    }  
    
    @keyframes bounceIn {  
      from {  
        opacity: 0;  
        transform: translateY(-15px);  
      }  
      to {  
        opacity: 1;  
        transform: translateY(0);  
      }  
    }  
  </style>  
</head>  
<body>  
  <header>  
    <h1>THE LOST WEB 🌟</h1>  
  </header>  
  <nav>  
    <a href="#home">Home</a>  
    <a href="#about">About</a>  
    <a href="#myself">Myself</a>  
    <a href="#blogs">Blogs</a>  
    <a href="#games">Games</a>  
    <a href="#thanks">Thank You</a>  
  </nav>  
  <section id="home">  
    <h2>Welcome!</h2>  
    <p>This is a fun and playful blog platform made just for you!</p>  
  </section>  
  <section id="about">  
    <h2>About</h2>  
    <p>This blog was created using love, creativity, and maybe a little code magic 🪄.</p>  
  </section>  
  <section id="myself">  
    <h2>Myself</h2>  
    <img src="5A6ABF91B5E13A4E907FE5B2CDCA7C31F748AD45" alt="Kamakshi" style="width: 120px; border-radius: 12px; display: block; margin: 0 auto 1em;">  
    <p>Hi there! I'm Kamakshi and this is my first time creating a website where I blog and maybe live. About myself I'm 18 and I'm very much interested in gaming and doing nothing but also a little bit of coding. I love making friends, and in person I maybe an extrovert but I'm not much confident if you ask me but that's ok. That's how life works right!?. I might not be perfect and neither is this website but I hope y'all like it 🙂. Thanks for being here. Toddles!</p>  
  </section>  
  <section id="blogs">  
    <h2>Latest Blogs</h2>  
    <div class="blog-entry">  
      <h3🎨 Blog 1♥️</h3>  
      <p> Its been a rough day and while blaming god for everything that's happening in my life I realised what the actual problem was and so here I'm discussing about THE REAL PROBLEM......with this poem----->    There's nothing more important to me than to be...
to live...to feel
but still the question echoes: is it truly necessary?
Alone without love, no tender care to cradle my heart,
seeking souls to halt this solitude, but shadows chase me still,
like demons dancing in the dark of my restless mind.
The world once sparkled bright in solitary glow,
but now I'm encircled by strangers whose hearts are void,
each glance a dagger, every word a wound,
they bury my hope deeper than any weapon can wound.
Innocence was my shroud, believing in binds of closeness,
convincing myself it’s me, that I’m the flaw,
but no, no, no—
I’m just a marionette, strings pulled for their delight,
yet I’ve grown; perhaps my heart remains a timid child,
screaming silently, longing to cry, longing to be whole,
and still I know, the mirror reflects the problem within me, cause yes! the problem is me.....

23/06/2025 </p>  
    </div>  
    <div class="blog-entry">  
      <h3>🎨 Blog 2♥️</h3>  
      <p> I've been realising lately that everything I do will never be enough or maybe...... I'M NOT ACTUALLY DOING ENOUGH------>

Crying in silence, running through pain,
Screaming inside like a voice in the rain.
I've given my all, done more than I could,
Yet still I'm unseen, misunderstood.

For those that I love, I’ve carried the weight,
Faced every storm, surrendered to fate.
But they look at me with eyes so cold,
And I’m lost in stories I've already told.

Lost in the past, in shadows I flee,
Trapped in a place I never wished to be.
I wonder aloud—what do I desire?
When did my soul lose its fire?

I’ve become someone I never planned,
A stranger shaped by unseen hands.
Not cruel, not heartless, not a foe—
Just tired, just broken, moving slow.

They say I’m wrong, they think I’m weak,
But maybe I’m just too soft to speak.
Maybe my love was never enough
To heal the cracks, to smooth the rough.

I’ve searched within, I’ve tried my best,
But some battles don’t end in rest.
Now I stand with nothing left to prove,
Just the ache of all I couldn’t move.

So if I seem like I’m drifting apart,
Know it’s not hate—it’s a heavy heart.
I gave my all, yet here I stand,
Still wondering if I was ever enough... in anyone’s hands......

24/06/2025 </p>  <h2>🎮 Let's Play Some Games!</h2>
    </div>  
  </section>  
  <section id="games"> 
    <div class="game-section" id="trivia">
  <h3>🎬 Bollywood Trivia</h3>
  <p id="triviaQuestion"></p>
  <div id="triviaChoices"></div>
  <p id="triviaFeedback"></p>
  <button onclick="nextTrivia()">Next</button>
</div>
      <div class="game-section" id="puzzle">
  <h3>🧩 Sliding Puzzle</h3>
  <div id="puzzleGrid" style="width:300px;height:300px;"></div>
  <button onclick="shufflePuzzle()">Shuffle</button>
</div>
    <div class="game-section" id="simon">
  <h3>💡 Simon Says</h3>
  <div id="simonCircles"></div>
  <div><button onclick="startSimon()">Start</button></div>
  <p id="simonMsg"></p>
</div>
    <div class="game-section" id="mole">
  <h3>👻 Whack-a-Mole</h3>
  <div id="moleGrid" style="display:grid;grid-template:repeat(3,100px)/repeat(3,100px);gap:5px;"></div>
  <p>Score: <span id="moleScore">0</span></p>
</div>
    <div class="game-section" id="catchEmojis">
  <h3>🍓 Catch Falling Emojis</h3>
  <canvas id="catchCanvas" width="300" height="300" style="border:1px solid #333;"></canvas>
  <p>Score: <span id="catchScore">0</span></p>
</div>
    <div class="game-section">  
      <h3>🎲 Dice Roller</h3>  
      <button onclick="rollDice()">Roll Dice</button>  
      <p id="diceResult"></p>  
    </div>  
    <div class="game-section">  
      <h3>🧠 Memory Match</h3>  
      <div class="memory-grid" id="memoryMatch"></div>  
    </div>  
    <div class="game-section">  
      <h3>✊ Rock Paper Scissors</h3>  
      <div class="rps-buttons">  
        <button onclick="playRPS('rock')">✊</button>  
        <button onclick="playRPS('paper')">✋</button>  
        <button onclick="playRPS('scissors')">✌️</button>  
      </div>  
      <p id="rpsResult"></p>  
    </div>  
    <div class="game-section">  
      <h3>🔤 Hangman (Word: CODE)</h3>  
      <p id="hangmanWord">_ _ _ _</p>  
      <input type="text" maxlength="1" id="hangmanInput">  
      <button onclick="guessLetter()">Guess</button>  
      <p id="hangmanMessage"></p>  
    </div>  
    <div class="game-section">  
      <h3>🌀 Maze (Coming Soon)</h3>  
      <p>A fun maze challenge will be added here!</p>  
    </div>  
  </section>  
  <section id="thanks">  
    <h2>Thank You!</h2>  
    <p>Thanks for visiting my blog. You're awesome! 🌟</p>  
  </section>  
  <footer>  
    <p>&copy; 2025 Playful Blog by You!</p>  
  </footer>  
  <script>  
    function rollDice() {  
      const result = Math.floor(Math.random() * 6) + 1;  
      document.getElementById('diceResult').textContent = `You rolled: ${result}`;  
    }  
    const emojis = ['🍓','🍓','🍇','🍇','🍍','🍍','🍉','🍉'];  
    let memoryState = [], flipped = [], matched = [];  
    function drawMemory() {  
      memoryState = [...emojis].sort(() => 0.5 - Math.random());  
      matched = [];  
      updateMemoryGrid();  
    }  
    function updateMemoryGrid() {  
      const grid = document.getElementById('memoryMatch');  
      grid.innerHTML = '';  
      memoryState.forEach((emoji, i) => {  
        const card = document.createElement('div');  
        card.className = 'memory-card';  
        card.textContent = matched.includes(i) || flipped.includes(i) ? emoji : '?';  
        card.onclick = () => flipCard(i);  
        grid.appendChild(card);  
      });  
    }  
    function flipCard(i) {  
      if (flipped.length < 2 && !flipped.includes(i) && !matched.includes(i)) {  
        flipped.push(i);  
        updateMemoryGrid();  
        if (flipped.length === 2) {  
          setTimeout(() => {  
            if (memoryState[flipped[0]] === memoryState[flipped[1]]) matched.push(...flipped);  
            flipped = [];  
            updateMemoryGrid();  
          }, 500);  
        }  
      }  
    }  
    drawMemory();  
    function playRPS(user) {  
      const choices = ['rock', 'paper', 'scissors'];  
      const computer = choices[Math.floor(Math.random() * 3)];  
      let result = '';  
      if (user === computer) result = "It's a tie!";  
      else if ((user === 'rock' && computer === 'scissors') || (user === 'paper' && computer === 'rock') || (user === 'scissors' && computer === 'paper')) result = 'You win! 🎉';  
      else result = 'Computer wins! 🤖';  
      document.getElementById('rpsResult').textContent = `You: ${user}, Computer: ${computer} → ${result}`;  
    }  
    const targetWord = 'CODE';  
    let guessed = ['_', '_', '_', '_'];  
    function guessLetter() {  
      const letter = document.getElementById('hangmanInput').value.toUpperCase();  
      document.getElementById('hangmanInput').value = '';  
      let correct = false;  
      for (let i = 0; i < targetWord.length; i++) {  
        if (targetWord[i] === letter) {  
          guessed[i] = letter;  
          correct = true;  
        }  
      }  
      document.getElementById('hangmanWord').textContent = guessed.join(' ');  
      document.getElementById('hangmanMessage').textContent = correct ? 'Correct!' : 'Try again!';  
    }  const colors=["red","green","blue","yellow"];
let simonSeq=[], userPos=0;

function startSimon(){
  simonSeq=[...Array(3)].map(()=>colors[Math.floor(Math.random()*4)]);
  userPos=0;
  document.getElementById('simonMsg').textContent="";
  playSimon(0);
}
function playSimon(i){
  const circles = document.getElementById('simonCircles');
  circles.innerHTML = colors.map(c=>`<div style="width:50px;height:50px;background:${c};display:inline-block;margin:5px;opacity:${i<0?'1':'0.3'}" onclick="userSimon('${c}')"></div>`).join('');
  if(i>=0 && i<simonSeq.length){
    setTimeout(()=>{
      circles.querySelectorAll('div')[colors.indexOf(simonSeq[i])].style.opacity=1;
      setTimeout(()=>playSimon(i+1),500);
    },500);
  } else {
    colors.forEach((c,i)=> circles.querySelectorAll('div')[i].style.opacity=1);
  }
}
function userSimon(col){
  if(col===simonSeq[userPos]){
    userPos++;
    if(userPos===simonSeq.length) document.getElementById('simonMsg').textContent="🎉 You won!";
  } else document.getElementById('simonMsg').textContent="❌ Try again!";
}const trivia = [
  { q: "Who played Bunny in 'Yeh Jawaani Hai Deewani'?", opts: ["Ranbir Kapoor","Shahid Kapoor","Varun Dhawan"], a: "Ranbir Kapoor" },
  { q: "Which movie features the song 'Tum Hi Ho'?", opts: ["Aashiqui 2","Kal Ho Na Ho","Barfi"], a: "Aashiqui 2" }
];
let tvIndex = 0;
function showTrivia(){
  const t = trivia[tvIndex];
  document.getElementById('triviaQuestion').textContent = t.q;
  document.getElementById('triviaChoices').innerHTML = t.opts.map(o=>`<button onclick="checkTrivia('${o}')">${o}</button>`).join('');
  document.getElementById('triviaFeedback').textContent = "";
}
function checkTrivia(ans){
  document.getElementById('triviaFeedback').textContent = ans === trivia[tvIndex].a ? "🎉 Correct!" : "❌ Oops!";
}
function nextTrivia(){
  tvIndex = (tvIndex+1)%trivia.length;
  showTrivia();
}
showTrivia();
let moleScore=0;
function setupMole(){
  const grid=document.getElementById('moleGrid');
  grid.innerHTML="";
  for(let i=0;i<9;i++){
    const cell=document.createElement('div');
    cell.style.border="1px solid #333"; cell.style.fontSize="2rem"; cell.style.textAlign="center";
    cell.onclick=()=>{ if(cell.innerText==="👻"){ moleScore++; updateMole(); } };
    grid.appendChild(cell);
  }
  setInterval(showMole,800);
}
function showMole(){
  [...document.getElementById('moleGrid').children].forEach(c=> c.innerText="");
  const i=Math.floor(Math.random()*9);
  document.getElementById('moleGrid').children[i].innerText="👻";
}
function updateMole(){
  document.getElementById('moleScore').textContent=moleScore;
}
setupMole();
const imgSrc="Screenshot_2025-06-25-01-50-38-68.jpg", N=3;
let puzzle=[];

function initPuzzle(){
  const grid=document.getElementById('puzzleGrid');
  grid.innerHTML="";
  puzzle=[...Array(N*N).keys()];
  puzzle.forEach((i, idx)=>{
    const div=document.createElement('div');
    div.style.width=(300/N)+"px";
    div.style.height=(300/N)+"px";
    div.style.background=`url(${imgSrc}) no-repeat -${(i%N)*100}px -${Math.floor(i/N)*100}px`;
    div.style.boxSizing="border-box";
    div.style.border="1px solid #555";
    div.onclick=()=>movePuzzle(idx);
    grid.appendChild(div);
  });
}
function shufflePuzzle(){
  for(let i=puzzle.length-1;i>0;i--){
    const j=Math.floor(Math.random()*(i+1));
    [puzzle[i],puzzle[j]]=[puzzle[j],puzzle[i]];
  }
  initPuzzle();
}
function movePuzzle(idx){
  // simplified: just reshuffle
  shufflePuzzle();
}
initPuzzle();
const catchCanvas = document.getElementById("catchCanvas");
const ctx = catchCanvas.getContext("2d");
let catchScore=0, basketX=150, items=[];
function startCatch(){
  setInterval(gameLoop,100);
  setInterval(() => items.push({x:Math.random()*280,y:0,emoji:['🍓','💖','🍒'][Math.floor(Math.random()*3)]}),800);
}
function gameLoop(){
  ctx.clearRect(0,0,300,300);
  ctx.fillRect(basketX,280,40,20);
  items.forEach((it, i)=>{
    it.y += 5;
    ctx.font="20px serif";
    ctx.fillText(it.emoji, it.x, it.y);
    if(it.y>280 && it.x>basketX && it.x<basketX+40){
      catchScore++; items.splice(i,1);
    }
  });
  document.getElementById('catchScore').textContent=catchScore;
}
catchCanvas.onclick = e => basketX = e.offsetX - 20;
startCatch();
  </script>  
</body>  
</html>
