<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>THE LOST WEB</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: #fef3c7;
      color: #333;
    }
    nav {
      background: #facc15;
      display: flex;
      justify-content: space-around;
      padding: 1em;
      position: sticky;
      top: 0;
      z-index: 1000;
    }
    nav a {
      text-decoration: none;
      color: #222;
      font-weight: bold;
      padding: 0.5em 1em;
      border-radius: 12px;
    }
    nav a:hover {
      background: #fde68a;
    }
    section {
      padding: 2em;
      border-bottom: 2px dashed #fcd34d;
    }
    h2 {
      color: #9333ea;
    }
    .game-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 2em;
    }
    .card {
      background: white;
      border-radius: 20px;
      padding: 1.5em;
      box-shadow: 2px 2px 12px #ccc;
      flex: 1 1 300px;
      min-height: 300px;
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
    #memory-board {
      display: grid;
      grid-template-columns: repeat(4, 50px);
      gap: 10px;
      justify-content: center;
      margin-top: 1em;
    }
    .flip-card {
      width: 50px;
      height: 50px;
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
  </style>
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
    <h2>Blog 1 ♥️</h2>
    <pre>Its been a rough day and while blaming god for everything that's happening in my life I realised what the actual problem was 
      and so here I'm discussing about THE REAL PROBLEM......with this poem----->
      There's nothing more important to me than to be... to live...to feel
      but still the question echoes: is it truly necessary? Alone without love, no tender care to cradle my heart, seeking souls to halt this solitude,
      but shadows chase me still, like demons dancing in the dark of my restless mind.
      The world once sparkled bright in solitary glow,
      but now I'm encircled by strangers whose hearts are void, each glance a dagger, every word a wound, they bury my hope deeper than any weapon can wound.
      Innocence was my shroud, believing in binds of closeness, convincing myself it’s me, 
      that I’m the flaw, but no, no, no— I’m just a marionette, strings pulled for their delight, 
      yet I’ve grown; perhaps my heart remains a timid child, screaming silently, longing to cry,
      longing to be whole, and still I know, the mirror reflects the problem within me, cause yes! the problem is me.....

23/06/2025</pre>
    <h2>Blog 2 ♥️</h2>
    <pre>I've been realising lately that everything I do will never be enough or maybe...... I'M NOT ACTUALLY DOING ENOUGH------>

Crying in silence, running through pain, Screaming inside like a voice in the rain. I've given my all, done more than I could, Yet still I'm unseen, misunderstood.

For those that I love, I’ve carried the weight, Faced every storm, surrendered to fate. But they look at me with eyes so cold, And I’m lost in stories I've already told.

Lost in the past, in shadows I flee, Trapped in a place I never wished to be. I wonder aloud—what do I desire? When did my soul lose its fire?

I’ve become someone I never planned, A stranger shaped by unseen hands. Not cruel, not heartless, not a foe— Just tired, just broken, moving slow.

They say I’m wrong, they think I’m weak, But maybe I’m just too soft to speak. Maybe my love was never enough To heal the cracks, to smooth the rough.

I’ve searched within, I’ve tried my best, But some battles don’t end in rest. Now I stand with nothing left to prove, Just the ache of all I couldn’t move.

So if I seem like I’m drifting apart, Know it’s not hate—it’s a heavy heart. I gave my all, yet here I stand, Still wondering if I was ever enough... in anyone’s hands......

24/06/2025</pre>
  </section>
  <section id="games">
    <h2>Games 🎮</h2>
    <div class="game-grid">
      <div class="card">
        <h3>Memory Game</h3>
        <div id="memory-board"></div>
        <button onclick="startMemoryGame()">Restart</button>
      </div>
    </div>
  </section>
  <audio id="flip-sound" src="https://cdn.pixabay.com/audio/2022/03/15/audio_aab9ac687e.mp3"></audio>
  <script>
    let memoryEmojis = ['🐱','🐶','🐵','🐸','🐼','🐷','🐯','🐰'];
    let memoryCards = [];
    let flipped = [], matched = [];function shuffle(array) {
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

  </script>
</body>
</html>
