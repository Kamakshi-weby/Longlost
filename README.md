<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>BLOG TIME!!</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      font-family: 'Comic Sans MS', cursive, sans-serif;
    }
    section {
  padding: 30px 20px;
  min-height: auto; /* or remove this line */
}
    h1, h2 {
      background: linear-gradient(90deg, #ff6ec4, #7873f5);
      color: white;
      padding: 10px;
      border-radius: 10px;
      text-align: center;
      margin-bottom: 20px;
    }
    #home { background-color: #FFD1DC; }
    #about { background-color: #B0E0E6; }
    #myself { background-color: #D8BFD8; }
    #blogs { background-color: #FFFACD; }
    #games { background-color: #E6E6FA; }
    #comeagain { background-color: #98FB98; }
    img.profile {
      max-width: 100px;
      border: 10px dotted pink;
      border-radius: 20px;
    }
    .game, .blog {
      margin: 20px auto;
      padding: 20px;
      border-radius: 20px;
      background: #fff;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      max-width: 500px;
      text-align: center;
    }
    .blog img {
      max-width: 100%;
      border-radius: 10px;
      margin-top: 10px;
    }
    .board, .memory-grid, .simon-buttons {
      display: grid;
      gap: 10px;
      justify-content: center;
      margin-top: 10px;
    }
    .board { grid-template-columns: repeat(3, 80px); }
    .memory-grid { grid-template-columns: repeat(4, 80px); }
    .memory-card, .cell, .simon-btn {
      width: 80px;
      height: 80px;
      font-size: 24px;
      border: 2px solid #000;
      border-radius: 10px;
    }
    .simon-btn { height: 60px; }
  </style>
</head>
<body><!-- Background music with toggle button -->
<audio id="bg-music" loop>
  <source src="https://cdn.pixabay.com/download/audio/2023/06/12/audio_f07ec2b64e.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>

<button onclick="toggleMusic()" style="position: fixed; top: 10px; right: 10px; z-index: 1000; background: #fff; border: 2px solid #ccc; border-radius: 10px; padding: 8px;">
  ▶️ Play Music
</button>

<script>
  const music = document.getElementById('bg-music');
  const button = document.querySelector('button');

  function toggleMusic() {
    if (music.paused) {
      music.play();
      button.textContent = '⏸️ Pause Music';
    } else {
      music.pause();
      button.textContent = '▶️ Play Music';
    }
  }
</script>
   </body>
  </audio>  <section id="home">
    <h1>Welcome to THE LOST WEB</h1>
    <p>Explore fun, colors, and creativity 🌈</p>
  </section>  <section id="about">
    <h1>About</h1>
    <p>This is a magical, colorful website full of joy, games, blogs, and a glimpse into my world.</p>
  </section>  <section id="myself">
    <h1>Myself</h1>
    <p> Hi there! I'm Kamakshi and this is my first time creating a website where I blog and maybe live. About myself I'm 18 and I'm very much interested in gaming and doing nothing but also a little bit of coding. I love making friends, and in person I maybe an extrovert but I'm not much confident if you ask me but that's ok. That's how life works right!?. I might not be perfect and neither is this website but I hope y'all like it 🙂. Thanks for being here. Toddles!</p>
    <img src="59ADAB5B393E06E454CAEEFBABF1AC83D49C1B14" alt="My Photo" class="profile">
  </section>  <section id="blogs">
    <h1>Blogs</h1>
    <div class="blog">
      <h2>Blog 1🌸</h2>
      <p> Its been a rough day and while blaming god for everything that's happening in my life I realised what the actual problem was and so here I'm discussing about THE REAL PROBLEM......with this poem-----> There's nothing more important to me than to be... to live...to feel but still the question echoes: is it truly necessary? Alone without love, no tender care to cradle my heart, seeking souls to halt this solitude, but shadows chase me still, like demons dancing in the dark of my restless mind. The world once sparkled bright in solitary glow, but now I'm encircled by strangers whose hearts are void, each glance a dagger, every word a wound, they bury my hope deeper than any weapon can wound. Innocence was my shroud, believing in binds of closeness, convincing myself it’s me, that I’m the flaw, but no, no, no— I’m just a marionette, strings pulled for their delight, yet I’ve grown; perhaps my heart remains a timid child, screaming silently, longing to cry, longing to be whole, and still I know, the mirror reflects the problem within me, cause yes! the problem is me.....

23/06/2025 </p>
      
    </div>
    <div class="blog">
      <h2>Blog 2🌸</h2>
      <p>  I've been realising lately that everything I do will never be enough or maybe...... I'M NOT ACTUALLY DOING ENOUGH------>

Crying in silence, running through pain, Screaming inside like a voice in the rain. I've given my all, done more than I could, Yet still I'm unseen, misunderstood.

For those that I love, I’ve carried the weight, Faced every storm, surrendered to fate. But they look at me with eyes so cold, And I’m lost in stories I've already told.

Lost in the past, in shadows I flee, Trapped in a place I never wished to be. I wonder aloud—what do I desire? When did my soul lose its fire?

I’ve become someone I never planned, A stranger shaped by unseen hands. Not cruel, not heartless, not a foe— Just tired, just broken, moving slow.

They say I’m wrong, they think I’m weak, But maybe I’m just too soft to speak. Maybe my love was never enough To heal the cracks, to smooth the rough.

I’ve searched within, I’ve tried my best, But some battles don’t end in rest. Now I stand with nothing left to prove, Just the ache of all I couldn’t move.

So if I seem like I’m drifting apart, Know it’s not hate—it’s a heavy heart. I gave my all, yet here I stand, Still wondering if I was ever enough... in anyone’s hands......

24/06/2025</p>
  
    </div>
  </section>  <section id="games">
    <h1>Games</h1><div class="game" id="tic-tac-toe">
  <h2>Tic Tac Toe</h2>
  <div class="board"></div>
</div>

<div class="game" id="memory-card">
  <h2>Memory Card Game</h2>
  <div class="memory-grid"></div>
</div>

<div class="game" id="simon-says">
  <h2>Simon Says</h2>
  <div class="simon-buttons"></div>
  <p id="simon-status"></p>
</div>

<div class="game" id="bollywood-trivia">
  <h2>Bollywood Trivia</h2>
  <p id="trivia-question"></p>
  <div id="trivia-options"></div>
  <p id="trivia-score"></p>
</div>

  </section>  <section id="comeagain">
    <h1>Come Again!</h1>
    <p>Thanks for visiting 💖<br>Come back again for more magic, colors, and fun!</p>
  </section>  <script>
    // Tic Tac Toe
    const board = document.querySelector('.board');
    let current = 'X';
    let cells = Array(9).fill(null);
    function checkWinner() {
      const wins = [
        [0,1,2],[3,4,5],[6,7,8],
        [0,3,6],[1,4,7],[2,5,8],
        [0,4,8],[2,4,6]
      ];
      for (let combo of wins) {
        const [a, b, c] = combo;
        if (cells[a] && cells[a] === cells[b] && cells[a] === cells[c]) return cells[a];
      }
      return cells.includes(null) ? null : 'Draw';
    }
    function drawBoard() {
      board.innerHTML = '';
      cells.forEach((val, i) => {
        const cell = document.createElement('button');
        cell.className = 'cell';
        cell.textContent = val || '';
        cell.onclick = () => {
          if (!cells[i]) {
            cells[i] = current;
            current = current === 'X' ? 'O' : 'X';
            drawBoard();
            const win = checkWinner();
            if (win) alert(win === 'Draw' ? 'Draw!' : win + ' wins!');
          }
        };
        board.appendChild(cell);
      });
    }
    drawBoard();

    // Memory Game
    const memoryGrid = document.querySelector('.memory-grid');
    const icons = ['🍎','🍌','🍓','🍇','🍒','🥝','🍍','🥥'];
    let memoryCards = [...icons, ...icons].sort(() => Math.random() - 0.5);
    let flipped = [], matched = [];
    function drawMemory() {
      memoryGrid.innerHTML = '';
      memoryCards.forEach((val, i) => {
        const btn = document.createElement('button');
        btn.className = 'memory-card';
        btn.textContent = matched.includes(i) || flipped.includes(i) ? val : '?';
        btn.onclick = () => {
          if (flipped.length < 2 && !flipped.includes(i) && !matched.includes(i)) {
            flipped.push(i);
            if (flipped.length === 2) {
              if (memoryCards[flipped[0]] === memoryCards[flipped[1]]) {
                matched.push(...flipped);
              }
              setTimeout(() => { flipped = []; drawMemory(); }, 500);
            }
            drawMemory();
          }
        };
        memoryGrid.appendChild(btn);
      });
    }
    drawMemory();

    // Simon Says
    const simonButtons = document.querySelector('.simon-buttons');
    const colors = ['Red', 'Green', 'Blue', 'Yellow'];
    const sequence = [];
    let playerIndex = 0;
    const status = document.getElementById('simon-status');
    colors.forEach(color => {
      const btn = document.createElement('button');
      btn.className = 'simon-btn';
      btn.style.backgroundColor = color.toLowerCase();
      btn.textContent = color;
      btn.onclick = () => handleSimonClick(color);
      simonButtons.appendChild(btn);
    });
    function playSimon() {
      const next = colors[Math.floor(Math.random()*colors.length)];
      sequence.push(next);
      showSimonSequence();
    }
    function showSimonSequence() {
      status.textContent = 'Watch...';
      let i = 0;
      const interval = setInterval(() => {
        status.textContent = sequence[i];
        i++;
        if (i >= sequence.length) {
          clearInterval(interval);
          status.textContent = 'Your turn!';
        }
      }, 800);
      playerIndex = 0;
    }
    function handleSimonClick(color) {
      if (color === sequence[playerIndex]) {
        playerIndex++;
        if (playerIndex === sequence.length) {
          status.textContent = 'Good job! Next round...';
          setTimeout(playSimon, 1000);
        }
      } else {
        status.textContent = 'Wrong! Game Over!';
        sequence.length = 0;
      }
    }
    playSimon();

    // Bollywood Trivia
    const triviaQuestions = [
      { q: 'Who played the role of Munna Bhai?', o: ['Aamir Khan', 'Salman Khan', 'Sanjay Dutt', 'Shahrukh Khan'], a: 'Sanjay Dutt' },
      { q: 'Which movie has the song "Kal Ho Naa Ho"?', o: ['Kabhi Khushi Kabhi Gham', 'Kal Ho Naa Ho', 'Veer Zaara', 'My Name is Khan'], a: 'Kal Ho Naa Ho' },
      // Add 23 more questions here...
    ];
    while (triviaQuestions.length < 25) {
      triviaQuestions.push({ q: 'Sample Q' + triviaQuestions.length, o: ['A', 'B', 'C', 'D'], a: 'A' });
    }
    let triviaIndex = 0, triviaScore = 0;
    const triviaQ = document.getElementById('trivia-question');
    const triviaOpts = document.getElementById('trivia-options');
    const triviaScoreBox = document.getElementById('trivia-score');
    function showTrivia() {
      let current = triviaQuestions[triviaIndex];
      triviaQ.textContent = current.q;
      triviaOpts.innerHTML = '';
      current.o.forEach(opt => {
        const btn = document.createElement('button');
        btn.textContent = opt;
        btn.onclick = () => {
          if (opt === current.a) triviaScore++;
          triviaIndex++;
          if (triviaIndex < triviaQuestions.length) showTrivia();
          else triviaQ.textContent = 'Quiz Over!';
          triviaScoreBox.textContent = `Score: ${triviaScore}/25`;
        };
        triviaOpts.appendChild(btn);
      });
    }
    showTrivia();
  </script></body>
</html>
