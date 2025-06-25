
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Cool Pastel Website</title>
  <style>
    .cute-border {
  width: 120px;
  height: auto;
  border: 5px dotted #ffafcc;
  border-radius: 15px;
  margin-top: 1rem;
  box-shadow: 0 0 15px #ffd6e0;
}
   body {
  margin: 0;
  font-family: 'Comic Sans MS', cursive, sans-serif;
  background: linear-gradient(135deg, #fcd5ce, #d0f4de, #ffc8dd, #b5ead7, #ffafcc);
  background-size: 400% 400%;
  animation: gradientMove 15s ease infinite;
  color: #444;
  text-align: center;
}

@keyframes gradientMove {
  0% {background-position: 0% 50%;}
  50% {background-position: 100% 50%;}
  100% {background-position: 0% 50%;}
} header, nav {
  background-color: #ffe5ec;
  padding: 1rem;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

nav a {
  margin: 0 1rem;
  text-decoration: none;
  font-weight: bold;
  color: #7a5c61;
  border-bottom: 2px solid transparent;
}

nav a:hover {
  border-bottom: 2px solid #ffb3c1;
}

h1, h2 {
  color: #6d6875;
  text-decoration: underline wavy #b5ead7;
}

section {
  margin: 2rem;
  padding: 1rem;
  background-color: #fff1f8;
  border-radius: 20px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.1);
}

canvas {
  border: 2px solid #a3c4f3;
  background-color: #f1faee;
}
section#about {
  background-color: #ffefef;
}
section#myself {
  background-color: #e5f4ff;
}
section#blogs {
  background-color: #fff0f5;
}
section#games {
  background-color: #eaf8e6;
}
section#bye {
  background-color: #ffe0fb;
}
background: linear-gradient(...);
background-size: 400% 400%;
animation: gradientMove 15s ease infinite;
  .sparkle {
  animation: sparkle 1s infinite alternate;
}
  </style>
</head>
<body><header>
  <h1 class="sparkle" style="color: #ff69b4;">
  ✨ Welcome to THE LOST WORLD ✨</h1>
  <nav>
    <a href="#about">About</a>
    <a href="#myself">Myself</a>
    <a href="#blogs">Blogs</a>
    <a href="#games">Games</a>
    <a href="#bye">Bye</a>
  </nav>
</header><section id="about">
  <h2>About</h2>
  <p> Welcome to my website where you can find sad, boring yet amazing blogs!❤️ </p>
</section><section id="myself">
  <h2>Myself</h2><img src="1730789421311.webp" alt="Kamakshi" style="width: 120px; border-radius: 12px; display: block; margin: 0 auto 1em;">
  <p> Hi there! I'm Kamakshi and this is my first time creating a website where I blog and maybe live. About myself I'm 18 and I'm very much interested in gaming and doing nothing but also a little bit of coding. I love making friends, and in person I maybe an extrovert but I'm not much confident if you ask me but that's ok. That's how life works right!?. I might not be perfect and neither is this website but I hope y'all like it 🙂. Thanks for being here. 
</section><section id="blogs">
  <h2>Blog 1🎨♥️</h2>
  <p> Its been a rough day and while blaming god for everything that's happening in my life I realised what the actual problem was and so here I'm discussing about THE REAL PROBLEM......with this poem-----> There's nothing more important to me than to be... to live...to feel but still the question echoes: is it truly necessary? Alone without love, no tender care to cradle my heart, seeking souls to halt this solitude, but shadows chase me still, like demons dancing in the dark of my restless mind. The world once sparkled bright in solitary glow, but now I'm encircled by strangers whose hearts are void, each glance a dagger, every word a wound, they bury my hope deeper than any weapon can wound. Innocence was my shroud, believing in binds of closeness, convincing myself it’s me, that I’m the flaw, but no, no, no— I’m just a marionette, strings pulled for their delight, yet I’ve grown; perhaps my heart remains a timid child, screaming silently, longing to cry, longing to be whole, and still I know, the mirror reflects the problem within me, cause yes! the problem is me.....

23/06/2025  </p>
<section id="blogs">
  <h2>Blog 2🎨♥️</h2>
    <p>I've been realising lately that everything I do will never be enough or maybe...... I'M NOT ACTUALLY DOING ENOUGH------>

Crying in silence, running through pain, Screaming inside like a voice in the rain. I've given my all, done more than I could, Yet still I'm unseen, misunderstood.

For those that I love, I’ve carried the weight, Faced every storm, surrendered to fate. But they look at me with eyes so cold, And I’m lost in stories I've already told.

Lost in the past, in shadows I flee, Trapped in a place I never wished to be. I wonder aloud—what do I desire? When did my soul lose its fire?

I’ve become someone I never planned, A stranger shaped by unseen hands. Not cruel, not heartless, not a foe— Just tired, just broken, moving slow.

They say I’m wrong, they think I’m weak, But maybe I’m just too soft to speak. Maybe my love was never enough To heal the cracks, to smooth the rough.

I’ve searched within, I’ve tried my best, But some battles don’t end in rest. Now I stand with nothing left to prove, Just the ache of all I couldn’t move.

So if I seem like I’m drifting apart, Know it’s not hate—it’s a heavy heart. I gave my all, yet here I stand, Still wondering if I was ever enough... in anyone’s hands......

24/06/2025 </p>
</section><section id="games">
  <h2>🎮 Fun Games Zone 🎮</h2>
  <ul>
    <li><a href="#" onclick="startBollywoodTrivia()">Bollywood Movie Trivia</a></li>
    <li><a href="#" onclick="startMemoryGame()">Memory Card Game</a></li>
    <li><a href="#" onclick="startRPS()">Rock Paper Scissors</a></li>
    <li><a href="#" onclick="startSimonSays()">Simon Says</a></li>
    <li><a href="#" onclick="startSnakeGame()">Snake Game</a></li>
  </ul>  <div id="gameContainer">
    <!-- Games will be rendered here -->
  </div>
</section><section id="bye">
  <h2>Bye</h2>
  <p>Thanks for visiting! Come back soon 🌟</p>
</section><script>
  function startBollywoodTrivia() {
    document.getElementById("gameContainer").innerHTML = '<p>🎬 Trivia game coming soon!</p>';
  }

  function startMemoryGame() {
    document.getElementById("gameContainer").innerHTML = '<p>🧠 Memory game coming soon!</p>';
  }

  function startRPS() {
    document.getElementById("gameContainer").innerHTML = `
      <h3>Rock Paper Scissors</h3>
      <button onclick="playRPS('rock')">🪨 Rock</button>
      <button onclick="playRPS('paper')">📄 Paper</button>
      <button onclick="playRPS('scissors')">✂️ Scissors</button>
      <p id="rpsResult"></p>`;
  }

  function playRPS(user) {
    const choices = ['rock', 'paper', 'scissors'];
    const computer = choices[Math.floor(Math.random() * 3)];
    let result = '';
    if (user === computer) result = "It's a tie!";
    else if ((user === 'rock' && computer === 'scissors') ||
             (user === 'paper' && computer === 'rock') ||
             (user === 'scissors' && computer === 'paper')) {
      result = "You win!";
    } else {
      result = "Computer wins!";
    }
    document.getElementById("rpsResult").textContent = `You: ${user} | Computer: ${computer} → ${result}`;
  }

  function startSimonSays() {
    document.getElementById("gameContainer").innerHTML = '<p>🟢 Simon Says game coming soon!</p>';
  }

  function startSnakeGame() {
    document.getElementById("gameContainer").innerHTML = '<p>🐍 Snake game coming soon!</p>';
  } 
  
</script></body>
</html>
