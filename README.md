# Longlost
My kind of world❤️
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
  </style>
</head>
<body>
  <header>
    <h1>THE LOST WEB 🌟</h1>
  </header>  <nav>
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#myself">Myself</a>
    <a href="#blogs">Blogs</a>
    <a href="#games">Games</a>
    <a href="#thanks">Thank You</a>
  </nav>  <section id="home">
    <h2>Welcome!</h2>
    <p>This is a fun and playful blog platform made just for you!</p>
  </section>  <section id="about">
    <h2>About</h2>
    <p>This blog was created using love, creativity, and maybe a little code magic 🪄.</p>
 <section id="myself">
  <h2>Myself</h2>
  <img src="5A6ABF91B5E13A4E907FE5B2CDCA7C31F748AD45" alt="Kamakshi" style="width: 120px; border-radius: 12px; display: block; margin: 0 auto 1em;">
  <p>Hi there! I'm Kamakshi and this is my first time creating a website where I blog and maybe live. About myself I'm 18 and I'm very much interested in gaming and doing nothing but also a little bit of coding. I love making friends, and in person I maybe an extrovert but I'm not much confident if you ask me but that's ok. That's how life works right!?. I might not perfect and neither is this website but I hope y'all like it 🙂. Thanks for being here. Toddles!</p>
 </section> <section id="blogs">
    <h2>Latest Blogs</h2>
    <div class="blog-entry">
      <h3>🎈 Blog Post One</h3>
      <p>This is the first post in the playful world of blogging. Stay tuned for more!</p>
    </div>
    <div class="blog-entry">
      <h3>🎨 Blog Post Two</h3>
      <p>Here's another post full of color, life, and good vibes.</p>
    </div>
  </section>  <section id="games">
    <h2>🎮 Let's Play Some Games!</h2><div class="game-section">
  <h3>🟡 Tic-Tac-Toe</h3>
  <div class="game-board" id="ticTacToe"></div>
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

  </section>  <section id="thanks">
    <h2>Thank You!</h2>
    <p>Thanks for visiting my blog. You're awesome! 🌟</p>
  </section>  <footer>
    <p>&copy; 2025 Playful Blog by You!</p>
  </footer>  <script>
    // Tic-Tac-Toe
    const board = Array(9).fill(null);
    let currentPlayer = 'X';
    const ttt = document.getElementById('ticTacToe');
    function drawBoard() {
      ttt.innerHTML = '';
      board.forEach((val, i) => {
        const cell = document.createElement('div');
        cell.className = 'cell';
        cell.textContent = val || '';
        cell.onclick = () => makeMove(i);
        ttt.appendChild(cell);
      });
    }
    function makeMove(i) {
      if (!board[i]) {
        board[i] = currentPlayer;
        currentPlayer = currentPlayer === 'X' ? 'O' : 'X';
        drawBoard();
      }
    }
    drawBoard();

    // Memory Match
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
        if (matched.includes(i) || flipped.includes(i)) {
          card.textContent = emoji;
        } else {
          card.textContent = '?';
        }
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
            if (memoryState[flipped[0]] === memoryState[flipped[1]]) {
              matched.push(...flipped);
            }
            flipped = [];
            updateMemoryGrid();
          }, 500);
        }
      }
    }
    drawMemory();

    // Rock Paper Scissors
    function playRPS(user) {
      const choices = ['rock', 'paper', 'scissors'];
      const computer = choices[Math.floor(Math.random() * 3)];
      let result = '';
      if (user === computer) result = "It's a tie!";
      else if ((user === 'rock' && computer === 'scissors') ||
               (user === 'paper' && computer === 'rock') ||
               (user === 'scissors' && computer === 'paper')) {
        result = 'You win! 🎉';
      } else {
        result = 'Computer wins! 🤖';
      }
      document.getElementById('rpsResult').textContent = `You: ${user}, Computer: ${computer} → ${result}`;
    }
  </script></body>
</html>
