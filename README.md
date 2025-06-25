
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>THE LOST WEB</title>
  <style>
    body {
      margin: 0;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background: linear-gradient(to right, #fbc2eb, #a6c1ee);
      color: #333;
      overflow-x: hidden;
    }
    header {
      background-color: #fff0f5;
      padding: 20px;
      text-align: center;
      font-size: 2em;
      color: #8e44ad;
    }
    section {
      padding: 40px 20px;
    }
.about-img {
  width: 80px !important;
  height: 80px !important;
  object-fit: cover;
  border: 3px dashed #ffb6c1;
  border-radius: 50%;
  display: block;
  margin: 10px auto;
}

    h2 {
      color: #6a0dad;
    }
    .game-area button {
      padding: 10px 20px;
      margin: 5px;
      font-size: 16px;
      border-radius: 10px;
      background: #ffe0f0;
      border: 2px solid #da70d6;
      cursor: pointer;
    }
    canvas {
      display: block;
      margin: 10px auto;
      background: #fff8dc;
    }
    @media (max-width: 450px) {
      header {
        font-size: 1.5em;
      }
    }
    .welcome-section {
  background: linear-gradient(to right, #ff6f61, #ffcc00);
  color: white;
  text-shadow: 2px 2px 4px #00000050;
  padding: 30px;
  font-size: 2.5em;
  border-bottom: 4px dashed #fff;
}

.about-section {
  background: linear-gradient(to right, #ffb347, #ffcc33);
}

.blog-section {
  background: linear-gradient(to right, #00c9ff, #92fe9d);
}

.game-section {
  background: linear-gradient(to right, #ff758c, #ff7eb3);
}
  </style>
</head>
<body>
  <audio autoplay loop>
    <source src="https://cdn.pixabay.com/audio/2022/03/15/audio_93cb55b9b5.mp3" type="audio/mpeg">
  </audio>
  <header>
    ✨ Welcome to Kamakshi's Website ✨
  </header>  <section id="about"><section id="blogs" class="blog-section">
<section id="games" class="game-section">
    <h2>About Myself</h2>
    <img src="59ADAB5B393E06E454CAEEFBABF1AC83D49C1B14" alt="My Image" class="about-img">
    <p>🧚‍♀️Hi there! I'm Kamakshi and this is my first time creating a website where I blog and maybe live. About myself I'm 18 and I'm very much interested in gaming and doing nothing but also a little bit of coding. I love making friends, and in person I maybe an extrovert but I'm not much confident if you ask me but that's ok. That's how life works right!?. I might not be perfect and neither is this website but I hope y'all like it 🙂. Thanks for being here. Toddles!🌸</p>
  </section>  <section id="blogs">
    <h2>Blogs♥️</h2>
    <div>
      <h3>Blog 1🎨</h3>
      <p>Its been a rough day and while blaming god for everything that's happening in my life I realised what the actual problem was and so here I'm discussing about THE REAL PROBLEM......with this poem-----> There's nothing more important to me than to be... to live...to feel but still the question echoes: is it truly necessary? Alone without love, no tender care to cradle my heart, seeking souls to halt this solitude, but shadows chase me still, like demons dancing in the dark of my restless mind. The world once sparkled bright in solitary glow, but now I'm encircled by strangers whose hearts are void, each glance a dagger, every word a wound, they bury my hope deeper than any weapon can wound. Innocence was my shroud, believing in binds of closeness, convincing myself it’s me, that I’m the flaw, but no, no, no— I’m just a marionette, strings pulled for their delight, yet I’ve grown; perhaps my heart remains a timid child, screaming silently, longing to cry, longing to be whole, and still I know, the mirror reflects the problem within me, cause yes! the problem is me.....

23/06/2025</p>
    </div>
    <div>
      <h3>BLOG 2🎨</h3>
      <p> I've been realising lately that everything I do will never be enough or maybe...... I'M NOT ACTUALLY DOING ENOUGH------>

Crying in silence, running through pain, Screaming inside like a voice in the rain. I've given my all, done more than I could, Yet still I'm unseen, misunderstood.

For those that I love, I’ve carried the weight, Faced every storm, surrendered to fate. But they look at me with eyes so cold, And I’m lost in stories I've already told.

Lost in the past, in shadows I flee, Trapped in a place I never wished to be. I wonder aloud—what do I desire? When did my soul lose its fire?

I’ve become someone I never planned, A stranger shaped by unseen hands. Not cruel, not heartless, not a foe— Just tired, just broken, moving slow.

They say I’m wrong, they think I’m weak, But maybe I’m just too soft to speak. Maybe my love was never enough To heal the cracks, to smooth the rough.

I’ve searched within, I’ve tried my best, But some battles don’t end in rest. Now I stand with nothing left to prove, Just the ache of all I couldn’t move.

So if I seem like I’m drifting apart, Know it’s not hate—it’s a heavy heart. I gave my all, yet here I stand, Still wondering if I was ever enough... in anyone’s hands......

24/06/2025 </p>
    </div>
  </section>  <section id="games">
    <h2>Games</h2><!-- Rock Paper Scissors -->
<div>
  <h3>Rock Paper Scissors</h3>
  <div class="game-area">
    <button onclick="playRPS('rock')">🪨 Rock</button>
    <button onclick="playRPS('paper')">📄 Paper</button>
    <button onclick="playRPS('scissors')">✂️ Scissors</button>
    <p id="rps-result"></p>
  </div>
</div>

<!-- Simon Says -->
<div>
  <h3>Simon Says</h3>
  <div id="simon-buttons" class="game-area"></div>
  <p id="simon-info"></p>
  <button onclick="startSimon()">Start Simon Game</button>
</div>


<!-- Bollywood Trivia -->
<div>
  <h3>Bollywood Trivia</h3>
  <div id="trivia-container">
    <p id="trivia-question"></p>
    <div id="trivia-options"></div>
    <p id="trivia-score"></p>
  </div>
  <button onclick="startTrivia()">Start Trivia</button>
</div>

  </section>  <script>
    // Rock Paper Scissors
    function playRPS(user) {
      const choices = ['rock', 'paper', 'scissors'];
      const computer = choices[Math.floor(Math.random() * 3)];
      let result = '';
      if (user === computer) result = "It's a tie!";
      else if ((user === 'rock' && computer === 'scissors') || (user === 'paper' && computer === 'rock') || (user === 'scissors' && computer === 'paper'))
        result = "You win!";
      else result = "You lose!";
      document.getElementById('rps-result').innerText = `You chose ${user}, computer chose ${computer}. ${result}`;
    }

    // Simon Says
    let simonSequence = [];
    let userSequence = [];
    function startSimon() {
      simonSequence = [];
      userSequence = [];
      nextSimonRound();
    }
    function nextSimonRound() {
      const colors = ['red', 'green', 'blue', 'yellow'];
      const newColor = colors[Math.floor(Math.random() * colors.length)];
      simonSequence.push(newColor);
      userSequence = [];
      renderSimonButtons();
      flashSequence();
    }
    function renderSimonButtons() {
      const container = document.getElementById('simon-buttons');
      container.innerHTML = '';
      ['red','green','blue','yellow'].forEach(color => {
        const btn = document.createElement('button');
        btn.style.background = color;
        btn.textContent = color;
        btn.onclick = () => handleSimonClick(color);
        container.appendChild(btn);
      });
    }
    function flashSequence() {
      let i = 0;
      const interval = setInterval(() => {
        document.getElementById('simon-info').innerText = `Simon says: ${simonSequence[i]}`;
        i++;
        if (i >= simonSequence.length) clearInterval(interval);
      }, 1000);
    }
    function handleSimonClick(color) {
      userSequence.push(color);
      const currentIndex = userSequence.length - 1;
      if (userSequence[currentIndex] !== simonSequence[currentIndex]) {
        document.getElementById('simon-info').innerText = 'Wrong move! Game Over.';
      } else if (userSequence.length === simonSequence.length) {
        document.getElementById('simon-info').innerText = 'Good job! Next round...';
        setTimeout(nextSimonRound, 1000);
      }
    }
   
    // Bollywood Trivia
    const triviaQuestions = [
      { q: "Which movie featured the song 'Tujhe Dekha To'?", a: "DDLJ", o: ["Kuch Kuch Hota Hai", "DDLJ", "Kabhi Khushi Kabhie Gham"] },
      { q: "Who played the lead in 'Bajrangi Bhaijaan'?", a: "Salman Khan", o: ["Aamir Khan", "Salman Khan", "Shah Rukh Khan"] },
      // (Add 23 more questions like this)
    ];
    let currentQ = 0;
    let score = 0;
    function startTrivia() {
      currentQ = 0;
      score = 0;
      showTrivia();
    }
    function showTrivia() {
      const q = triviaQuestions[currentQ];
      document.getElementById('trivia-question').innerText = q.q;
      const container = document.getElementById('trivia-options');
      container.innerHTML = '';
      q.o.forEach(opt => {
        const btn = document.createElement('button');
        btn.innerText = opt;
        btn.onclick = () => checkTrivia(opt);
        container.appendChild(btn);
      });
    }
    function checkTrivia(ans) {
      if (ans === triviaQuestions[currentQ].a) score++;
      currentQ++;
      if (currentQ < triviaQuestions.length) {
        showTrivia();
      } else {
        document.getElementById('trivia-score').innerText = `Your score: ${score}/${triviaQuestions.length}`;
      }
    }
  </script></body>
</html>
