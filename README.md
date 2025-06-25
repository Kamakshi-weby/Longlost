
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>THE LOST WEB</title>
  <style>
  #games .game-block {
  background: white;
  margin: 20px auto;
  padding: 20px;
  border-radius: 25px;
  box-shadow: 0 4px 20px rgba(0,0,0,0.1);
  max-width: 800px;
  width: 90%;
  overflow-x: auto;
}

@media (max-width: 768px) {
  #games .game-block {
    width: 95%;
    padding: 15px;
    margin: 15px auto;
  }

  canvas, iframe {
    width: 100% !important;
    height: auto !important;
  }
}

/* 🔶 Bright backgrounds for About & Myself curved blocks */
#about .curved-block {
  background: linear-gradient(to right, #fff000, #adff2f);
  padding: 30px;
  border-radius: 30px;
  color: #222;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
}

#myself .curved-block {
  background: linear-gradient(to right, #ffea00, #76ff03);
  padding: 30px;
  border-radius: 30px;
  color: #222;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
}

/* 🔶 Optional: full section background color too */
#about {
  background-color: #fff700;
}

#myself {
  background-color: #caff70;
}

/* 🔷 Game blocks responsive fix */
#games .game-block {
  background: white;
  margin: 20px auto;
  padding: 20px;
  border-radius: 25px;
  box-shadow: 0 4px 20px rgba(0,0,0,0.1);
  max-width: 800px;
  width: 90%;
  overflow-x: auto;
}

@media (max-width: 768px) {
  #games .game-block {
    width: 95%;
    padding: 15px;
    margin: 15px auto;
  }

  canvas, iframe {
    width: 100% !important;
    height: auto !important;
  }
}

    .navbar {
  position: sticky;
  top: 0;
  background: linear-gradient(to right, #ff9a9e, #fad0c4, #fad0c4, #fbc2eb, #a18cd1);
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 12px 0;
  z-index: 1000;
  box-shadow: 0 4px 6px rgba(0,0,0,0.1);
  flex-wrap: wrap;
}

.navbar a {
  color: white;
  text-decoration: none;
  font-weight: bold;
  font-family: 'Comic Sans MS', cursive;
  font-size: 16px;
  padding: 8px 16px;
  background: rgba(255,255,255,0.2);
  border-radius: 25px;
  transition: background 0.3s ease;
}

.navbar a:hover {
  background: rgba(255,255,255,0.5);
}
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      font-family: 'Comic Sans MS', cursive, sans-serif;
    }
    section {
      padding: 30px;
    }
    h1, h2 {
      background: linear-gradient(90deg, #ff6ec4, #7873f5);
      color: white;
      padding: 10px;
      border-radius: 10px;
      text-align: center;
      margin-bottom: 20px;
    }
    #home { background: #FFD1DC; }
    #about { background: #B0E0E6; }
    #myself { background: #D8BFD8; }
    #blogs { background: #FFFACD; }
    #games { background: #E6E6FA; }
    #comeagain { background: #98FB98; }
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
  #home {
  background: linear-gradient(to bottom right, #FFD1DC, #FFE4E1);
}
#about {
  background: linear-gradient(to bottom right, #B0E0E6, #AFEEEE);
}
#myself {
  background: linear-gradient(to bottom right, #D8BFD8, #E6E6FA);
}
.curved-block {
  background: linear-gradient(to right, #ffecd2, #fcb69f);
  padding: 30px;
  border-radius: 30px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
  max-width: 90%;
  margin: auto;
  margin-top: 20px;
  margin-bottom: 20px;
}
#about .curved-block {
  background: linear-gradient(to right, #fff000, #adff2f); /* Bright yellow to green */
  padding: 30px;
  border-radius: 30px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
  color: #222; /* Dark text for good contrast */
  max-width: 90%;
  margin: auto;
  margin-top: 20px;
  margin-bottom: 20px;
}

#myself .curved-block {
  background: linear-gradient(to right, #ffea00, #76ff03); /* Warm yellow to neon green */
  padding: 30px;
  border-radius: 30px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
  color: #222;
  max-width: 90%;
  margin: auto;
  margin-top: 20px;
  margin-bottom: 20px;
}
#about {
  background: #fff710;
}


</style>
</head>
<body><nav class="navbar">
  <ul>
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#myself">Myself</a></li>
    <li><a href="#blogs">Blogs</a></li>
    <li><a href="#games">Games</a></li>
    <li><a href="#come-again">Come Again</a></li>
  </ul>
</nav>
<header>

    <section id="home">
    <h1>Welcome to Kamakshi's website</h1>
    <p>🌈Explore my blogs....if you want to!🌈</p>
  <section id="about">
   <div class="curved block"> <h1>About</h1>
    <p>This is a magical, colorful website full of joy, games, blogs, and a glimpse of my world ♥️😴</p>
    <section id="myself">
   <div class="curved block"> <h1>Myself</h1>
    <p>😊 Hi there! I'm Kamakshi and this is my first time creating a website where I blog and maybe live. About myself, I'm 18 and I'm very much interested in gaming and doing nothing but also a little bit of coding. I love making friends, and in person I maybe an extrovert but I'm not much confident if you ask me but that's ok. That's how life works right!?. I might not be perfect and neither is this website but I hope y'all like it 🙂. Thanks for being here. Toddles!</p>
    <img src="59ADAB5B393E06E454CAEEFBABF1AC83D49C1B14" alt="My Photo" class="profile">
    <section id="blogs">
    <h1>Blogs</h1>
    <div class="blog">
      <h2>Blog 1🌸</h2>
      <p>Its been a rough day and while blaming god for everything that's happening in my life I realised what the actual problem was and so here I'm discussing about THE REAL PROBLEM......with this poem-----> There's nothing more important to me than to be... to live...to feel but still the question echoes: is it truly necessary? Alone without love, no tender care to cradle my heart, seeking souls to halt this solitude, but shadows chase me still, like demons dancing in the dark of my restless mind. The world once sparkled bright in solitary glow, but now I'm encircled by strangers whose hearts are void, each glance a dagger, every word a wound, they bury my hope deeper than any weapon can wound. Innocence was my shroud, believing in binds of closeness, convincing myself it’s me, that I’m the flaw, but no, no, no— I’m just a marionette, strings pulled for their delight, yet I’ve grown; perhaps my heart remains a timid child, screaming silently, longing to cry, longing to be whole, and still I know, the mirror reflects the problem within me, cause yes! the problem is me.....

23/06/2025</p>
    </div>
    <div class="blog">
      <h2>Blog 2🌸</h2>
      <p>I've been realising lately that everything I do will never be enough or maybe...... I'M NOT ACTUALLY DOING ENOUGH------>

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
    <h1>Games</h1>
    <div class="game" id="tic-tac-toe">
      <h2>Tic Tac Toe</h2>
      <div class="board"></div>
    </div><div class="game" id="memory-game">
  <h2>Memory Match</h2>
  <div class="memory-grid"></div>
</div>

<div class="game" id="simon-game">
  <h2>Simon Says</h2>
  <div class="simon-buttons">
    <button class="simon-btn" style="background:red" onclick="press('red')">Red</button>
    <button class="simon-btn" style="background:green" onclick="press('green')">Green</button>
    <button class="simon-btn" style="background:blue" onclick="press('blue')">Blue</button>
    <button class="simon-btn" style="background:yellow" onclick="press('yellow')">Yellow</button>
  </div>
  <p id="simon-status"></p>
</div>

<div class="game" id="trivia">
  <h2>Bollywood Trivia</h2>
  <div id="trivia-question"></div>
  <div id="trivia-options"></div>
  <p id="trivia-feedback"></p>
</div>

  </section>  <section id="comeagain">
    <h1>Come Again!</h1>
    <p>Thank you for visiting. Hope to see you again soon 💖</p>
  </section>  

  <script> // Tic Tac Toe
    const board = document.querySelector('.board');
    let currentPlayer = 'X';
    let cells = Array(9).fill('');
    board.innerHTML = '';
    cells.forEach((_, i) => {
      const btn = document.createElement('button');
      btn.className = 'cell';
      btn.onclick = () => {
        if (btn.textContent === '') {
          btn.textContent = currentPlayer;
          cells[i] = currentPlayer;
          currentPlayer = currentPlayer === 'X' ? 'O' : 'X';
        }
      };
      board.appendChild(btn);
    });

    // Memory Game
    const emojis = ['🍎','🍌','🍇','🍓','🍒','🍍','🥝','🍉'];
    const memoryGrid = document.querySelector('.memory-grid');
    let memory = [...emojis, ...emojis].sort(() => Math.random() - 0.5);
    let first = null, second = null;
    memory.forEach((item, i) => {
      const card = document.createElement('button');
      card.className = 'memory-card';
      card.textContent = '?';
      card.onclick = () => {
        if (card.textContent !== '?') return;
        card.textContent = item;
        if (!first) {
          first = { index: i, card };
        } else {
          second = { index: i, card };
          if (memory[first.index] === memory[second.index]) {
            first = second = null;
          } else {
            setTimeout(() => {
              first.card.textContent = '?';
              second.card.textContent = '?';
              first = second = null;
            }, 600);
          }
        }
      };
      memoryGrid.appendChild(card);
    });

    // Simon Says
    let simonSeq = [], playerSeq = [];
    function nextSimonColor() {
      const colors = ['red','green','blue','yellow'];
      const color = colors[Math.floor(Math.random() * 4)];
      simonSeq.push(color);
      document.getElementById('simon-status').textContent = 'Watch: ' + simonSeq.join(', ');
      playerSeq = [];
    }
    nextSimonColor();
    function press(color) {
      playerSeq.push(color);
      const currentIndex = playerSeq.length - 1;
      if (playerSeq[currentIndex] !== simonSeq[currentIndex]) {
        document.getElementById('simon-status').textContent = 'Wrong! Restarting...';
        simonSeq = [];
        setTimeout(() => nextSimonColor(), 1000);
      } else if (playerSeq.length === simonSeq.length) {
        document.getElementById('simon-status').textContent = 'Correct! Next round...';
        setTimeout(() => nextSimonColor(), 1000);
      }
    }

    // Bollywood Trivia
    const trivia = [
      {q: 'Who played the lead in Dangal?', a: 'Aamir Khan', o: ['Salman Khan','Aamir Khan','SRK','Ranbir']},
      {q: 'Movie with the song "Tujh Mein Rab Dikhta Hai"?', a: 'Rab Ne Bana Di Jodi', o: ['DDLJ','Rab Ne Bana Di Jodi','Veer-Zaara','Kal Ho Naa Ho']},
      {q: 'Who directed "3 Idiots"?', a: 'Rajkumar Hirani', o: ['Karan Johar','Rohit Shetty','Rajkumar Hirani','Anurag Kashyap']},
     { q: "What house is Harry Potter sorted into?", o: ["Hufflepuff", "Slytherin", "Gryffindor", "Ravenclaw"], a: "Gryffindor" },
{ q: "What is the name of Harry's owl?", o: ["Crookshanks", "Hedwig", "Scabbers", "Errol"], a: "Hedwig" },
{ q: "Who is the Half-Blood Prince?", o: ["Harry Potter", "Tom Riddle", "Severus Snape", "Albus Dumbledore"], a: "Severus Snape" },
{ q: "What is the spell to disarm an opponent?", o: ["Expelliarmus", "Avada Kedavra", "Lumos", "Alohomora"], a: "Expelliarmus" },
{ q: "What magical object shows your deepest desire?", o: ["Mirror of Erised", "Invisibility Cloak", "Pensieve", "Time-Turner"], a: "Mirror of Erised" },
{ q: "What position does Harry play on the Quidditch team?", o: ["Beater", "Chaser", "Keeper", "Seeker"], a: "Seeker" },
{ q: "Who is the headmaster of Hogwarts for most of the series?", o: ["Severus Snape", "Minerva McGonagall", "Albus Dumbledore", "Remus Lupin"], a: "Albus Dumbledore" },
{ q: "What does the Marauder's Map say when it closes?", o: ["All done", "Mischief Managed", "Goodbye!", "I solemnly swear"], a: "Mischief Managed" },
{ q: "Which creature guards the vaults at Gringotts?", o: ["Dragon", "Goblin", "Troll", "House-elf"], a: "Goblin" },
{ q: "What form does Harry's Patronus take?", o: ["Stag", "Phoenix", "Dog", "Otter"], a: "Stag" },
  { q: "Which Bollywood movie is based on the life of mathematician Anand Kumar?", o: ["Super 30", "Chhichhore", "MS Dhoni", "Taare Zameen Par"], a: "Super 30" },
{ q: "Who played the female lead in the movie 'Queen'?", o: ["Alia Bhatt", "Kangana Ranaut", "Deepika Padukone", "Kareena Kapoor"], a: "Kangana Ranaut" },
{ q: "Which actor is known as the 'King of Bollywood'?", o: ["Aamir Khan", "Salman Khan", "Shahrukh Khan", "Akshay Kumar"], a: "Shahrukh Khan" },
{ q: "What is the name of the school in 'Taare Zameen Par'?", o: ["New Era High", "Greenfield", "Tulip International", "Boarding House"], a: "Boarding House" },
{ q: "Which movie featured the dialogue 'Mogambo khush hua'?", o: ["Sholay", "Don", "Mr. India", "Dilwale Dulhania Le Jayenge"], a: "Mr. India" },
{ q: "Who composed the music for 'Dilwale Dulhania Le Jayenge'?", o: ["A.R. Rahman", "Anu Malik", "Jatin-Lalit", "Pritam"], a: "Jatin-Lalit" },
{ q: "Which Bollywood actor is known for the role of 'Circuit'?", o: ["Sanjay Dutt", "Arshad Warsi", "Boman Irani", "Riteish Deshmukh"], a: "Arshad Warsi" },
{ q: "Which movie has the song 'Tujh Mein Rab Dikhta Hai'?", o: ["Rab Ne Bana Di Jodi", "Veer Zaara", "Kal Ho Naa Ho", "Kabir Singh"], a: "Rab Ne Bana Di Jodi" },
{ q: "What is the profession of Aamir Khan's character in '3 Idiots'?", o: ["Scientist", "Engineer", "Professor", "Inventor"], a: "Engineer" },
{ q: "Which movie is based on the life of Indian boxer Mary Kom?", o: ["Chak De India", "Sultan", "Mary Kom", "Dangal"], a: "Mary Kom" },
{ q: "Who directed the movie 'Lagaan'?", o: ["Ashutosh Gowariker", "Karan Johar", "Rajkumar Hirani", "Anurag Kashyap"], a: "Ashutosh Gowariker" },
{ q: "Which film features the character 'Geet'?", o: ["Tamasha", "Barfi", "Jab We Met", "Yeh Jawaani Hai Deewani"], a: "Jab We Met" },
{ q: "In 'Dangal', what sport is central to the story?", o: ["Boxing", "Cricket", "Wrestling", "Athletics"], a: "Wrestling" },
{ q: "Which movie has the character Rancho?", o: ["Student of the Year", "3 Idiots", "PK", "Taare Zameen Par"], a: "3 Idiots" },
{ q: "Which actress played the lead role in 'Raazi'?", o: ["Katrina Kaif", "Alia Bhatt", "Anushka Sharma", "Kareena Kapoor"], a: "Alia Bhatt" },    
      // Add up to 25 questions
    ];
    let index = 0;
    const questionEl = document.getElementById('trivia-question');
    const optionsEl = document.getElementById('trivia-options');
    const feedbackEl = document.getElementById('trivia-feedback');

    function showTrivia() {
      const current = trivia[index];
      questionEl.textContent = current.q;
      optionsEl.innerHTML = '';
      current.o.forEach(opt => {
        const btn = document.createElement('button');
        btn.textContent = opt;
        btn.onclick = () => {
          feedbackEl.textContent = opt === current.a ? '✅ Correct!' : '❌ Wrong!';
          index = (index + 1) % trivia.length;
          setTimeout(showTrivia, 1000);
        };
        optionsEl.appendChild(btn);
      });
    }
    showTrivia();
  </script><script>
  function toggleMusic() {
    const music = document.getElementById('bg-music');
    const button = document.querySelector('button');
    if (music.paused) {
      music.play();
      button.textContent = '⏸️ Pause Music';
    } else {
      music.pause();
      button.textContent = '▶️ Play Music';
    }
  }
</script>
