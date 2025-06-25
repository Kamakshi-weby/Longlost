// Kamakshi's Full Website Code // React + Tailwind with full games and colorful backgrounds

import React, { useState, useEffect } from 'react'; import { BrowserRouter as Router, Routes, Route, Link } from 'react-router-dom'; import './index.css';

// Navbar const Navbar = () => (

  <nav className="bg-yellow-400 text-black flex justify-between items-center px-6 py-4 shadow-md">
    <h1 className="text-xl font-bold">THE LOST WORLD 🌸</h1>
    <ul className="flex gap-4 text-md">
      <li><Link to="/">Home</Link></li>
      <li><Link to="/about">About</Link></li>
      <li><Link to="/me">Me</Link></li>
      <li><Link to="/blogs">Blogs</Link></li>
      <li><Link to="/games">Game</Link></li>
    </ul>
  </nav>
);// Pages const Home = () => (

  <div className="p-6 text-center bg-orange-100 min-h-screen">
    <h2 className="text-3xl font-bold mb-4">Welcome to My World! 🎉</h2>
    <p>This is a space where I share thoughts, games, and vibes. Dive in and enjoy!</p>
  </div>
);const About = () => (

  <div className="p-6 bg-blue-100 min-h-screen">
    <h2 className="text-2xl font-semibold mb-2">About This Website</h2>
    <p>This site is my creative outlet where I write blogs, share games, and just vibe online with a splash of color and chaos.</p>
  </div>
);const Me = () => (

  <div className="p-6 text-center bg-pink-100 min-h-screen">
    <img src="/images/Screenshot_2025-06-25-01-50-38-68.jpg" alt="Kamakshi" className="mx-auto rounded-2xl w-48 h-48 mb-4" />
    <p className="text-lg">Hi there! I'm Kamakshi and this is my first time creating a website where I blog and maybe live. I'm 18 and I'm very much interested in gaming and doing nothing but also a little bit of coding. I love making friends, and in person I maybe an extrovert but I'm not much confident if you ask me but that's ok. That's how life works right!?. I might not be perfect and neither is this website but I hope y'all like it 🙂. Thanks for being here. Toddles!</p>
  </div>
);const Blogs = () => (

  <div className="p-6 space-y-10 bg-green-100 min-h-screen">
    <div className="bg-white p-4 rounded-xl shadow-md">
      <h3 className="text-xl font-bold">Blog 1 ♥️</h3>
      <p className="mt-2">Its been a rough day and while blaming god for everything that's happening in my life I realised what the actual problem was and so here I'm discussing about THE REAL PROBLEM......</p>
      <pre className="mt-2 whitespace-pre-wrap">{`There's nothing more important to me than to be... to live...to feel
but still the question echoes: is it truly necessary?
...cause yes! the problem is me.....23/06/2025}</pre> </div> <div className="bg-white p-4 rounded-xl shadow-md"> <h3 className="text-xl font-bold">Blog 2 ♥️</h3> <p className="mt-2">I've been realising lately that everything I do will never be enough or maybe...... I'M NOT ACTUALLY DOING ENOUGH------></p> <pre className="mt-2 whitespace-pre-wrap">{Crying in silence, running through pain, ...Still wondering if I was ever enough... in anyone’s hands......

24/06/2025`}</pre> </div>

  </div>
);// GAME COMPONENTS const TicTacToe = () => { const [board, setBoard] = useState(Array(9).fill(null)); const [xIsNext, setXIsNext] = useState(true); const winner = calculateWinner(board); function handleClick(i) { if (board[i] || winner) return; const newBoard = board.slice(); newBoard[i] = xIsNext ? 'X' : 'O'; setBoard(newBoard); setXIsNext(!xIsNext); } function restart() { setBoard(Array(9).fill(null)); setXIsNext(true); } return ( <div> <div className="grid grid-cols-3 gap-1 w-36 mx-auto"> {board.map((val, i) => ( <button key={i} onClick={() => handleClick(i)} className="w-12 h-12 bg-white text-2xl font-bold border-2">{val}</button> ))} </div> <p className="text-center mt-2">{winner ? Winner: ${winner} : Next Player: ${xIsNext ? 'X' : 'O'}}</p> <button onClick={restart} className="mt-2 block mx-auto bg-purple-400 px-4 py-1 rounded">Restart</button> </div> ); }; function calculateWinner(squares) { const lines = [ [0, 1, 2], [3, 4, 5], [6, 7, 8], [0, 3, 6], [1, 4, 7], [2, 5, 8], [0, 4, 8], [2, 4, 6], ]; for (let [a, b, c] of lines) { if (squares[a] && squares[a] === squares[b] && squares[a] === squares[c]) return squares[a]; } return null; }

const MemoryGame = () => { const cards = ['🐶', '🐱', '🐭', '🐶', '🐱', '🐭']; const [shuffled, setShuffled] = useState([]); const [flipped, setFlipped] = useState([]); const [matched, setMatched] = useState([]); useEffect(() => { setShuffled(cards.sort(() => 0.5 - Math.random())); }, []); function flipCard(index) { if (flipped.length === 2 || flipped.includes(index)) return; const newFlipped = [...flipped, index]; setFlipped(newFlipped); if (newFlipped.length === 2) { const [first, second] = newFlipped; if (shuffled[first] === shuffled[second]) { setMatched([...matched, first, second]); setFlipped([]); } else { setTimeout(() => setFlipped([]), 1000); } } } return ( <div className="grid grid-cols-3 gap-2"> {shuffled.map((card, index) => ( <div key={index} onClick={() => flipCard(index)} className="w-16 h-16 bg-white text-2xl flex items-center justify-center border rounded" > {flipped.includes(index) || matched.includes(index) ? card : '?'}</div> ))} </div> ); };

const SimonSays = () => { const colors = ['red', 'blue', 'green', 'yellow']; const [sequence, setSequence] = useState([]); const [userInput, setUserInput] = useState([]); const [message, setMessage] = useState('');

const addToSequence = () => { const newColor = colors[Math.floor(Math.random() * 4)]; setSequence(prev => [...prev, newColor]); setUserInput([]); }; const handleClick = color => { const newInput = [...userInput, color]; setUserInput(newInput); const currentIndex = newInput.length - 1; if (newInput[currentIndex] !== sequence[currentIndex]) { setMessage('Wrong! Try again.'); setSequence([]); setUserInput([]); } else if (newInput.length === sequence.length) { setMessage('Good job!'); setTimeout(addToSequence, 1000); } }; useEffect(() => { addToSequence(); }, []); return ( <div> <p className="mb-2">Follow the pattern!</p> <div className="grid grid-cols-2 gap-2 w-48 mx-auto"> {colors.map(color => ( <button key={color} onClick={() => handleClick(color)} className={w-20 h-20 rounded ${color === 'red' ? 'bg-red-500' : color === 'blue' ? 'bg-blue-500' : color === 'green' ? 'bg-green-500' : 'bg-yellow-400'}}></button> ))} </div> <p className="mt-2 text-center">{message}</p> </div> ); };

const BollywoodTrivia = () => { const questions = [ { q: 'Who is known as the King of Bollywood?', a: ['Salman Khan', 'Aamir Khan', 'Shah Rukh Khan', 'Akshay Kumar'], correct: 2 }, { q: 'Which movie won Best Film at Filmfare 2023?', a: ['RRR', 'Gully Boy', 'Pathaan', 'Jawan'], correct: 3 } ]; const [index, setIndex] = useState(0); const [score, setScore] = useState(0); const [showResult, setShowResult] = useState(false); function answer(i) { if (i === questions[index].correct) setScore(score + 1); if (index + 1 < questions.length) setIndex(index + 1); else setShowResult(true); } return ( <div> {!showResult ? ( <div> <h4 className="font-bold">{questions[index].q}</h4> <div className="grid grid-cols-2 gap-2 mt-2"> {questions[index].a.map((opt, i) => ( <button onClick={() => answer(i)} className="bg-white border rounded p-1">{opt}</button> ))} </div> </div> ) : <p>Your Score: {score}/{questions.length}</p>} </div> ); };

const Games = () => (

  <div className="p-6 grid gap-6 md:grid-cols-2 bg-purple-100 min-h-screen">
    <div className="bg-pink-300 p-4 rounded-xl shadow-lg">
      <h3 className="text-xl font-bold mb-2">Tic Tac Toe</h3>
      <TicTacToe />
    </div>
    <div className="bg-green-300 p-4 rounded-xl shadow-lg">
      <h3 className="text-xl font-bold mb-2">Memory Card Game</h3>
      <MemoryGame />
    </div>
    <div className="bg-blue-300 p-4 rounded-xl shadow-lg">
      <h3 className="text-xl font-bold mb-2">Simon Says</h3>
      <SimonSays />
    </div>
    <div className="bg-yellow-300 p-4 rounded-xl shadow-lg">
      <h3 className="text-xl font-bold mb-2">Bollywood Trivia</h3>
      <BollywoodTrivia />
    </div>
  </div>
);// App export default function App() { return ( <Router> <Navbar /> <Routes> <Route path="/" element={<Home />} /> <Route path="/about" element={<About />} /> <Route path="/me" element={<Me />} /> <Route path="/blogs" element={<Blogs />} /> <Route path="/games" element={<Games />} /> </Routes> </Router> ); }

