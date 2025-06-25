<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>THE LOST WEB</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(135deg, #fcd34d, #f9a8d4, #a5f3fc);
      background-size: 400% 400%;
      animation: gradientMove 15s ease infinite;
      color: #333;
    }
    @keyframes gradientMove {
      0% {background-position: 0% 50%;}
      50% {background-position: 100% 50%;}
      100% {background-position: 0% 50%;}
    }
    nav {
      background: #7c3aed;
      display: flex;
      justify-content: space-around;
      padding: 1em;
      position: sticky;
      top: 0;
      z-index: 1000;
      color: white;
    }
    nav a {
      text-decoration: none;
      color: white;
      font-weight: bold;
      padding: 0.5em 1em;
      border-radius: 12px;
    }
    nav a:hover {
      background: #a78bfa;
    }
    section {
      padding: 2em;
      border-bottom: 2px dashed #f3f4f6;
    }
    h2 {
      color: #4c1d95;
    }
    .game-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 2em;
      justify-content: center;
    }
    .card {
      background: white;
      border-radius: 20px;
      padding: 1.5em;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      flex: 1 1 300px;
      min-height: 300px;
      transition: transform 0.3s;
    }
    .card:hover {
      transform: scale(1.03);
    }
    button {
      background-color: #a5f3fc;
      border: none;
      padding: 0.5em 1em;
      border-radius: 8px;
      cursor: pointer;
      margin: 0.2em;
      transition: transform 0.2s ease;
    }
    button:hover {
      background-color: #67e8f9;
      transform: scale(1.1);
    }
    #ttt-board button {
      width: 50px;
      height: 50px;
      font-size: 1.5em;
    }
    #memory-board {
      display: grid;
      grid-template-columns: repeat(4, 60px);
      gap: 10px;
      justify-content: center;
    }
    #simon-buttons button {
      width: 80px;
      height: 40px;
      color: white;
      font-weight: bold;
    }
    .flip-card {
      width: 60px;
      height: 60px;
      perspective: 1000px;
    }
    .flip-inner {
      position: relative;
      width: 100%;
      height: 100%;
      text-align: center;
      transition: transform 0.6s;
      transform-style: preserve-3d;
    }
    .flipped .flip-inner {
      transform: rotateY(180deg);
    }
    .flip-front, .flip-back {
      position: absolute;
      width: 100%;
      height: 100%;
      backface-visibility: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.5em;
      border-radius: 8px;
      background: #fef9c3;
    }
    .flip-back {
      transform: rotateY(180deg);
    }
#blogs {
  background: linear-gradient(135deg, #a5b4fc, #fca5a5); /* purple to pink */
  border-radius: 30px;
  padding: 2em;
  margin: 2em;
  line-height: 1.6;
  color: #222;
}

.blog-post {
  background: rgba(255, 255, 255, 0.8);
  margin-bottom: 2em;
  padding: 1.5em;
  border-radius: 20px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}/* Curved & colorful section backgrounds */
#home {
  background: linear-gradient(135deg, #fcd34d, #fbbf24); /* Golden */
  border-radius: 30px;
  padding: 2em;
  margin: 2em;
}

#about {
  background: linear-gradient(135deg, #6ee7b7, #3b82f6); /* Mint to blue */
  border-radius: 30px;
  padding: 2em;
  margin: 2em;
}

#me {
  background: linear-gradient(135deg, #f472b6, #e879f9); /* Pink to violet */
  border-radius: 30px;
  padding: 2em;
  margin: 2em;
}

#blogs {
  background: linear-gradient(135deg, #a5b4fc, #fca5a5); /* Soft purple to peach */
  border-radius: 30px;
  padding: 2em;
  margin: 2em;
}

#games {
  background: linear-gradient(135deg, #fcd34d, #a78bfa); /* Golden to purple */
  border-radius: 30px;
  padding: 2em;
  margin: 2em;
}  </style>
</head>
<body>
  <nav>
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#me">Me</a>
    <a href="#blogs">Blogs</a>
    <a href="#games">Games</a>
  </nav>
  <section id="home">
    <h2>Welcome 🌸</h2>
    <p>This is my cozy corner on the internet where I blog, game, and vibe. You're invited!</p>
  </section>
  <section id="about">
    <h2>About</h2>
    <p>This website is where I pour my heart out — with blogs and games, all made by me!</p>
  </section>
  <section id="me">
    <h2>About Me</h2>
    <img src="Screenshot_2025-06-25-01-50-38-68.jpg" alt="Kamakshi" width="150" style="border-radius: 50%;">
    <p>Hi there! I'm Kamakshi and this is my first time creating a website where I blog and maybe live. I'm 18 and I'm very much interested in gaming and doing nothing but also a little bit of coding. I love making friends, and in person I maybe an extrovert but I'm not much confident if you ask me but that's ok. That's how life works right!?. I might not be perfect and neither is this website but I hope y'all like it 🙂. Thanks for being here. Toddles!</p>
  </section>
  <section id="blogs">
    <h2>Blog 1 ♥️</h2><div class="blog-pst">
    <pre> Its been a rough day and while blaming god for everything that's happening in my life
 I realised what the actual problem was and so here I'm discussing about THE REAL PROBLEM....
 with this poem-----> 
 There's nothing more important to me than to be... to live...to feel 
 but still the question echoes: is it truly necessary?
 Alone without love, no tender care to cradle my heart, seeking souls to halt this solitude,
 but shadows chase me still, like demons dancing in the dark of my restless mind.
 The world once sparkled bright in solitary glow, but now I'm encircled by strangers whose hearts are void,
 each glance a dagger, every word a wound, they bury my hope deeper than any weapon can wound. 
 Innocence was my shroud, believing in binds of closeness, convincing myself it’s me, that I’m the flaw, 
 but no, no, no— I’m just a marionette, strings pulled for their delight, yet I’ve grown; perhaps my heart remains a timid    child,
 screaming silently, longing to cry, longing to be whole, and still I know, the mirror reflects the problem within me,
 cause yes! the problem is me.....

 23/06/2025</pre></pre></div>
    <h2>Blog 2 ♥️</h2><div class="blog-pst">
    <pre>I've been realising lately that everything I do will never be enough or maybe...... I'M NOT ACTUALLY DOING ENOUGH------>

Crying in silence, running through pain, Screaming inside like a voice in the rain. I've given my all, done more than I could, Yet still I'm unseen, misunderstood.

For those that I love, I’ve carried the weight, Faced every storm, surrendered to fate. But they look at me with eyes so cold, And I’m lost in stories I've already told.

Lost in the past, in shadows I flee, Trapped in a place I never wished to be. I wonder aloud—what do I desire? When did my soul lose its fire?

I’ve become someone I never planned, A stranger shaped by unseen hands. Not cruel, not heartless, not a foe— Just tired, just broken, moving slow.

They say I’m wrong, they think I’m weak, But maybe I’m just too soft to speak. Maybe my love was never enough To heal the cracks, to smooth the rough.

I’ve searched within, I’ve tried my best, But some battles don’t end in rest. Now I stand with nothing left to prove, Just the ache of all I couldn’t move.

So if I seem like I’m drifting apart, Know it’s not hate—it’s a heavy heart. I gave my all, yet here I stand, Still wondering if I was ever enough... in anyone’s hands......

24/06/2025</pre></div>
  </section>
  <section id="games">
    <h2>Games 🎮</h2>
    <div class="game-grid">
      <div class="card">
        <h3>Tic Tac Toe</h3>
        <div id="ttt-board"></div>
        <button onclick="tttRestart()">Restart</button>
      </div>
      <div class="card">
        <h3>Memory Game</h3>
        <div id="memory-board"></div>
        <button onclick="startMemoryGame()">Restart</button>
      </div>
      <div class="card">
        <h3>Simon Says</h3>
        <p id="simon-msg"></p>
        <div id="simon-buttons"></div>
        <button onclick="startSimon()">Start Game</button>
      </div>
      <div class="card">
        <h3>Bollywood Trivia</h3>
        <div id="trivia"></div>
      </div>
    </div>
  </section>
  <audio id="flip-sound" src="https://cdn.pixabay.com/audio/2022/03/15/audio_aab9ac687e.mp3"></audio>
  <script>
    // TIC TAC TOE
    let tttBoard = Array(9).fill('');
    let tttCurrent = 'X';
    const tttContainer = document.getElementById('ttt-board');
    function renderTTT() {
      tttContainer.innerHTML = '';
      tttBoard.forEach((val, i) => {
        const btn = document.createElement('button');
        btn.textContent = val;
        btn.onclick = () => {
          if (!tttBoard[i]) {
            tttBoard[i] = tttCurrent;
            tttCurrent = tttCurrent === 'X' ? 'O' : 'X';
            renderTTT();
            const win = checkWin();
            if (win) alert(`${win} wins!`);
          }
        };
        tttContainer.appendChild(btn);
      });
    }
    function tttRestart() {
      tttBoard = Array(9).fill('');
      tttCurrent = 'X';
      renderTTT();
    }
    function checkWin() {
      const lines = [
        [0,1,2],[3,4,5],[6,7,8],
        [0,3,6],[1,4,7],[2,5,8],
        [0,4,8],[2,4,6]
      ];
      for (const [a,b,c] of lines) {
        if (tttBoard[a] && tttBoard[a] === tttBoard[b] && tttBoard[a] === tttBoard[c]) return tttBoard[a];
      }
      return null;
    }
    renderTTT();// MEMORY GAME
let memoryEmojis = ['🐱','🐶','🐵','🐸','🐼','🐷','🐯','🐰'];
let memoryCards = [];
let flipped = [], matched = [];
function shuffle(array) {
  for (let i = array.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [array[i], array[j]] = [array[j], array[i]];
  }
  return array;
}
function startMemoryGame() {
  memoryCards = shuffle([...memoryEmojis, ...memoryEmojis]);
  flipped = [];
  matched = [];
  renderMemory();
}
function renderMemory() {
  const board = document.getElementById('memory-board');
  board.innerHTML = '';
  memoryCards.forEach((val, i) => {
    const card = document.createElement('div');
    card.className = 'flip-card';
    const inner = document.createElement('div');
    inner.className = 'flip-inner';
    if (flipped.includes(i) || matched.includes(i)) card.classList.add('flipped');

    const front = document.createElement('div');
    front.className = 'flip-front';
    front.textContent = '❓';

    const back = document.createElement('div');
    back.className = 'flip-back';
    back.textContent = val;

    inner.appendChild(front);
    inner.appendChild(back);
    card.appendChild(inner);

    card.onclick = () => {
      if (flipped.length < 2 && !flipped.includes(i) && !matched.includes(i)) {
        flipped.push(i);
        document.getElementById('flip-sound').play();
        renderMemory();
        if (flipped.length === 2) {
          setTimeout(() => {
            if (memoryCards[flipped[0]] === memoryCards[flipped[1]]) {
              matched.push(...flipped);
            }
            flipped = [];
            renderMemory();
            if (matched.length === memoryCards.length) {
              setTimeout(() => alert('🎉 You matched all the animals!'), 200);
            }
          }, 1000);
        }
      }
    };
    board.appendChild(card);
  });
}
startMemoryGame();

// SIMON SAYS
let simonSeq = [], simonInput = [];
const colors = ['red','green','blue','yellow'];
const msg = document.getElementById('simon-msg');
function startSimon() {
  simonSeq.push(colors[Math.floor(Math.random()*4)]);
  simonInput = [];
  showSimon();
}
function showSimon() {
  const container = document.getElementById('simon-buttons');
  container.innerHTML = '';
  colors.forEach(c => {
    const btn = document.createElement('button');
    btn.style.background = c;
    btn.textContent = c;
    btn.onclick = () => handleSimon(c);
    container.appendChild(btn);
  });
  msg.textContent = `Repeat this pattern: ${simonSeq.join(' → ')}`;
}
function handleSimon(c) {
  simonInput.push(c);
  if (simonInput[simonInput.length-1] !== simonSeq[simonInput.length-1]) {
    msg.textContent = 'Oops! Wrong move. Game Over 💥';
    simonSeq = [];
  } else if (simonInput.length === simonSeq.length) {
    msg.textContent = 'Yay! You got it! ✨';
    setTimeout(startSimon, 1000);
  }
}

// BOLLYWOOD TRIVIA
const triviaQ = [
  { q: 'Who is the King of Bollywood?', o: ['Salman', 'SRK', 'Aamir', 'Ranbir'], a: 1 },
  { q: 'Which movie won Filmfare 2023?', o: ['RRR', 'Pathaan', 'Jawan', 'Gully Boy'], a: 2 },
  { q: 'Which actress is called "Desi Girl"?', o: ['Katrina', 'Priyanka', 'Alia', 'Deepika'], a: 1 },
  { q: 'Who played the role of Munna Bhai?', o: ['Aamir Khan', 'Salman Khan', 'Sanjay Dutt', 'Shah Rukh Khan'], a: 2 },
  { q: 'Which movie has the song "Kal Ho Naa Ho"?', o: ['Veer-Zaara', 'Kal Ho Naa Ho', 'Kabhi Khushi Kabhie Gham', 'Dil Se'], a: 1 },
  { q: 'Which actor starred in "Dangal"?', o: ['Salman Khan', 'Akshay Kumar', 'Aamir Khan', 'Ajay Devgn'], a: 2 },
  { q: 'Who directed "Kabir Singh"?', o: ['Sandeep Vanga', 'Karan Johar', 'Rohit Shetty', 'Zoya Akhtar'], a: 0 },
  { q: 'What is the real name of Govinda?', o: ['Ravi Kapoor', 'Govind Ahuja', 'Sunil Shetty', 'Rakesh Roshan'], a: 1 },
  { q: 'Which film is based on hockey?', o: ['Chak De India', 'Dangal', 'Lagaan', 'Mary Kom'], a: 0 },
  { q: 'Who played Bajirao in "Bajirao Mastani"?', o: ['Ranbir Kapoor', 'Hrithik Roshan', 'Ranveer Singh', 'Shahid Kapoor'], a: 2 },
  { q: 'In which year did "Sholay" release?', o: ['1975', '1980', '1982', '1970'], a: 0 },
  { q: 'What is Katrina Kaif\'s debut movie?', o: ['Boom', 'Namastey London', 'Maine Pyaar Kyun Kiya', 'Zindagi Na Milegi Dobara'], a: 0 },
  { q: 'Which movie has the character Geet?', o: ['Barfi!', 'Jab We Met', 'Queen', 'Tamasha'], a: 1 },
  { q: 'Who composed the music for "Dil Se"?', o: ['Pritam', 'Shankar-Ehsaan-Loy', 'A.R. Rahman', 'Vishal-Shekhar'], a: 2 },
  { q: 'Who is called Mr. Perfectionist in Bollywood?', o: ['Shah Rukh Khan', 'Hrithik Roshan', 'Aamir Khan', 'Saif Ali Khan'], a: 2 },
  { q: 'Which movie features the song "Tujh Mein Rab Dikhta Hai"?', o: ['Rab Ne Bana Di Jodi', 'Dilwale', 'Jab Tak Hai Jaan', 'Fan'], a: 0 },
  { q: 'What is the profession of Shahid in "Kabir Singh"?', o: ['Lawyer', 'Doctor', 'Engineer', 'Singer'], a: 1 },
  { q: 'Which actor was in "Andaz Apna Apna"?', o: ['Govinda', 'Aamir & Salman', 'Ajay Devgn', 'Saif & SRK'], a: 1 },
  { q: 'Who played the lead in "Raazi"?', o: ['Deepika', 'Kangana', 'Alia Bhatt', 'Kareena'], a: 2 },
  { q: 'Which movie is India\'s official entry to Oscars 2022?', o: ['RRR', 'Chhello Show', 'The Kashmir Files', 'Rocketry'], a: 1 },
  { q: 'What is the highest-grossing Indian film ever?', o: ['PK', 'Dangal', 'Baahubali 2', 'Pathaan'], a: 2 },
  { q: 'Who played the character of Kabir in "War"?', o: ['Tiger Shroff', 'Hrithik Roshan', 'Ranveer Singh', 'Shahid Kapoor'], a: 1 },
  { q: 'Which film was based on surgical strikes?', o: ['Uri', 'Shershaah', 'Raazi', 'Attack'], a: 0 },
  { q: 'Which actor is known for his dance?', o: ['Nawazuddin', 'Hrithik Roshan', 'Aamir Khan', 'Pankaj Tripathi'], a: 1 },
  { q: 'Which actress debuted in "Student of the Year"?', o: ['Kriti Sanon', 'Kiara Advani', 'Alia Bhatt', 'Sara Ali Khan'], a: 2 },
  { q: 'What role did Akshay play in "Toilet"?', o: ['Villain', 'Reporter', 'Social Worker', 'Husband'], a: 3 },
  { q: 'Which movie stars SRK & Kajol in Europe?', o: ['Dilwale', 'DDLJ', 'Kabhi Khushi...', 'My Name is Khan'], a: 1 },
  { q: 'Who is the director of "RRR"?', o: ['Rajkumar Hirani', 'Rohit Shetty', 'SS Rajamouli', 'Zoya Akhtar'], a: 2 },
  { q: 'What does "PK" stand for in the movie?', o: ['Pakistani Kid', 'Peekay (Drunk)', 'Pintu Kumar', 'None'], a: 1 },
  { q: 'Which movie has the line: "How\'s the Josh?"', o: ['Shershaah', 'Bhuj', 'Uri', 'Kesari'], a: 2 }
];
let tIndex = 0, score = 0;
function renderTrivia() {
  const box = document.getElementById('trivia');
  if (tIndex >= triviaQ.length) {
    box.innerHTML = `🎉 You scored ${score}/${triviaQ.length}`;
    return;
  }
  const q = triviaQ[tIndex];
  box.innerHTML = `<p>${q.q}</p>`;
  q.o.forEach((opt, i) => {
    const btn = document.createElement('button');
    btn.textContent = opt;
    btn.onclick = () => {
      if (i === q.a) score++;
      tIndex++;
      renderTrivia();
    };
    box.appendChild(btn);
  });
}
renderTrivia();

  </script>
</body>
</html>
