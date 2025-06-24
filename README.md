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
      <h3>🎈 Blog 1♥️</h3>  
      <p>Poem about life's struggles...</p>  
    </div>  
    <div class="blog-entry">  
      <h3>🎨 Blog 2♥️</h3>  
      <p>Realization about feeling inadequate...</p>  
    </div>  
  </section>  
  <section id="games">  
    <h2>🎮 Let's Play Some Games!</h2>  
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
    }  
  </script>  
</body>  
</html>
