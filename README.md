<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Pastel Fun World</title>
  <style>
    body {
      margin: 0;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background: linear-gradient(135deg, #fcd5ce, #d0f4de);
      color: #444;
      text-align: center;
    }header, nav {
  background-color: #ffe5ec;
  padding: 1rem;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

nav a {
  margin: 0 1rem;
  text-decoration: none;
  font-weight: bold;
  color: #7a5c61;
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
  max-width: 100%;
  height: auto;
}

.memory-card {
  width: 100px;
  height: 100px;
  background: #eee;
  display: inline-block;
  margin: 5px;
  font-size: 2em;
  vertical-align: top;
  line-height: 100px;
  cursor: pointer;
  border-radius: 10px;
}

button {
  padding: 10px 15px;
  margin: 5px;
  font-size: 1em;
  border-radius: 10px;
  border: none;
  background: #cdb4db;
  color: white;
}

audio {
  display: none;
}

@media (max-width: 600px) {
  nav a {
    display: block;
    margin: 0.5rem 0;
  }

  .memory-card {
    width: 70px;
    height: 70px;
    font-size: 1.5em;
    line-height: 70px;
  }
}

  </style>
</head>
<body>
  <audio autoplay loop>
    <source src="https://files.freemusicarchive.org/storage-freemusicarchive-org/music/no_curator/Scott_Buckley/This_Too_Shall_Pass/Scott_Buckley_-_01_-_Balloons.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
  </audio>  <header>
    <h1>✨ Welcome to THE LOST WORLD ✨</h1>
    <nav>
      <a href="#about">About</a>
      <a href="#myself">Myself</a>
      <a href="#blogs">Blogs</a>
      <a href="#games">Games</a>
      <a href="#bye">Bye</a>
    </nav>
  </header>  <section id="about">
    <h2>About</h2>
    <p>This site is a fun and vibrant place filled with pastels, games, and creativity!</p>
  </section>  <section id="myself">
    <h2>Myself</h2>
    <p>Hi there! I'm Kamakshi and this is my first time creating a website where I blog and maybe live. About myself I'm 18 and I'm very much interested in gaming and doing nothing but also a little bit of coding. I love making friends, and in person I maybe an extrovert but I'm not much confident if you ask me but that's ok. That's how life works right!?. I might not be perfect and neither is this website but I hope y'all like it 🙂. Thanks for being here. Toddles!🌸</p>
  </section>  <section id="blogs">
    <h2>Blog 1🎨</h2>
    <p> Its been a rough day and while blaming god for everything that's happening in my life I realised what the actual problem was and so here I'm discussing about THE REAL PROBLEM......with this poem-----> There's nothing more important to me than to be... to live...to feel but still the question echoes: is it truly necessary? Alone without love, no tender care to cradle my heart, seeking souls to halt this solitude, but shadows chase me still, like demons dancing in the dark of my restless mind. The world once sparkled bright in solitary glow, but now I'm encircled by strangers whose hearts are void, each glance a dagger, every word a wound, they bury my hope deeper than any weapon can wound. Innocence was my shroud, believing in binds of closeness, convincing myself it’s me, that I’m the flaw, but no, no, no— I’m just a marionette, strings pulled for their delight, yet I’ve grown; perhaps my heart remains a timid child, screaming silently, longing to cry, longing to be whole, and still I know, the mirror reflects the problem within me, cause yes! the problem is me.....

23/06/2025 </p>
<h2>Blog 2🎨</h2>
    <p>Its been a rough day and while blaming god for everything that's happening in my life I realised what the actual problem was and so here I'm discussing about THE REAL PROBLEM......with this poem-----> There's nothing more important to me than to be... to live...to feel but still the question echoes: is it truly necessary? Alone without love, no tender care to cradle my heart, seeking souls to halt this solitude, but shadows chase me still, like demons dancing in the dark of my restless mind. The world once sparkled bright in solitary glow, but now I'm encircled by strangers whose hearts are void, each glance a dagger, every word a wound, they bury my hope deeper than any weapon can wound. Innocence was my shroud, believing in binds of closeness, convincing myself it’s me, that I’m the flaw, but no, no, no— I’m just a marionette, strings pulled for their delight, yet I’ve grown; perhaps my heart remains a timid child, screaming silently, longing to cry, longing to be whole, and still I know, the mirror reflects the problem within me, cause yes! the problem is me.....

23/06/2025</p>
  </section>  <section id="games">
    <h2>🎮 Fun Games Zone 🎮</h2>
    <ul>
      <li><a href="#" onclick="startMemoryGame()">Memory Card Game</a></li>
      <li><a href="#" onclick="startSnakeGame()">Snake Game</a></li>
      <li><a href="#" onclick="startRPS()">Rock Paper Scissors</a></li>
      <li><a href="#" onclick="startTrivia()">Movie Trivia Quiz</a></li>
    </ul>
    <div id="gameContainer"></div>
  </section>  <section id="bye">
    <h2>Bye</h2>
    <p>Thanks for visiting! Come back soon 🌟</p>
  </section>  <script>
    // memory game (same as before)
    // snake game (same as before)

    function startRPS() {
      document.getElementById("gameContainer").innerHTML = `
        <h3>Rock Paper Scissors</h3>
        <button onclick="playRPS('rock')">🪨 Rock</button>
        <button onclick="playRPS('paper')">📄 Paper</button>
        <button onclick="playRPS('scissors')">✂️ Scissors</button>
        <p id="rpsResult"></p>
      `;
    }

    function playRPS(user) {
      const choices = ['rock', 'paper', 'scissors'];
      const computer = choices[Math.floor(Math.random() * 3)];
      let result = '';
      if (user === computer) result = "It's a tie!";
      else if ((user === 'rock' && computer === 'scissors') ||
               (user === 'paper' && computer === 'rock') ||
               (user === 'scissors' && computer === 'paper')) {
        result = `You win! ${user} beats ${computer}`;
      } else {
        result = `You lose! ${computer} beats ${user}`;
      }
      document.getElementById("rpsResult").innerText = result;
    }

    function startTrivia() {
      const questions = [
        { q: "Who played Iron Man in the Marvel movies?", a: "Robert Downey Jr." },
        { q: "Which movie is known for the quote 'I'll be back'?", a: "The Terminator" },
        { q: "Which movie won Best Picture in 2020?", a: "Parasite" },
        { q: "Which Disney movie features the song 'Let It Go'?", a: "Frozen" },
        { q: "Who directed 'Inception'?", a: "Christopher Nolan" },
        { q: "What is the name of Harry Potter's owl?", a: "Hedwig" },
        { q: "Who played Joker in 'The Dark Knight'?", a: "Heath Ledger" },
        { q: "Which animated movie has characters named Woody and Buzz?", a: "Toy Story" },
        { q: "Who directed Titanic?", a: "James Cameron" },
        { q: "In which movie does Tom Hanks talk to a volleyball?", a: "Cast Away" },
        { q: "Which superhero is from Wakanda?", a: "Black Panther" },
        { q: "Which movie is famous for the line 'Why so serious?'", a: "The Dark Knight" },
        { q: "Who is the female lead in 'La La Land'?", a: "Emma Stone" },
        { q: "Which film features time-loop 'Groundhog Day'?", a: "Groundhog Day" },
        { q: "Who voiced Dory in Finding Nemo?", a: "Ellen DeGeneres" },
        { q: "Which wizarding school does Harry Potter attend?", a: "Hogwarts" },
        { q: "Which movie has the quote 'Life is like a box of chocolates'?", a: "Forrest Gump" },
        { q: "What is the name of Simba’s evil uncle?", a: "Scar" },
        { q: "Who plays Jack in Titanic?", a: "Leonardo DiCaprio" },
        { q: "Which movie features 'Hakuna Matata'?", a: "The Lion King" },
      ];

      let current = 0;
      let score = 0;

      function showQuestion() {
        if (current >= questions.length) {
          document.getElementById("gameContainer").innerHTML = `<h3>Quiz Completed!</h3><p>Your score: ${score}/${questions.length}</p>`;
          return;
        }
        const q = questions[current];
        document.getElementById("gameContainer").innerHTML = `
          <h3>Trivia Question ${current + 1}</h3>
          <p>${q.q}</p>
          <input id="answerInput" placeholder="Your answer..." />
          <button onclick="checkAnswer()">Submit</button>
          <p id="feedback"></p>
        `;
      }

      window.checkAnswer = function() {
        const userAnswer = document.getElementById("answerInput").value.trim();
        if (userAnswer.toLowerCase() === questions[current].a.toLowerCase()) {
          score++;
          document.getElementById("feedback").innerText = "Correct!";
        } else {
          document.getElementById("feedback").innerText = `Wrong! Correct: ${questions[current].a}`;
        }
        current++;
        setTimeout(showQuestion, 1000);
      };

      showQuestion();
    }
  </script></body>
</html>
