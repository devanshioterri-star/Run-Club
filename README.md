```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Motivation Shuffle</title>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Merriweather:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      background: linear-gradient(to bottom right, #3b82f6, #fb923c);
      color: white;
      font-family: sans-serif;
    }
    h1 {
      font-size: 5rem;
      font-family: 'Bebas Neue', sans-serif;
      margin-bottom: 1.5rem;
    }
    button {
      background: white;
      color: #2563eb;
      font-weight: 600;
      padding: 0.75rem 1.5rem;
      border: none;
      border-radius: 1rem;
      cursor: pointer;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      transition: transform 0.2s;
    }
    button:hover {
      transform: scale(1.05);
    }
    .quote {
      font-size: 1.5rem;
      font-style: italic;
      font-family: 'Merriweather', serif;
      margin-bottom: 1rem;
    }
    .author {
      font-size: 1rem;
      font-weight: 300;
    }
    .gif-container {
      width: 300px;
      height: 300px;
      margin: 0 auto;
    }
  </style>
</head>
<body>
  <div id="app">
    <h1 id="title">Too Tired to Run?</h1>
    <button id="startBtn">Tap for instant motivation</button>
    <div id="gifContainer" class="gif-container" style="display:none;">
      <img src="https://media.tenor.com/_kWuTrzT4o8AAAAC/lets-go-outside-exercise.gif" alt="Running Girl GIF" width="100%" height="100%" />
    </div>
    <div id="quoteBox" style="display:none;">
      <p id="quote" class="quote"></p>
      <p id="author" class="author"></p>
      <button id="againBtn">Try Again</button>
    </div>
  </div>

  <script>
    const QUOTES = [
      { text: "Run into your unknown.", author: "Becs Gentry" },
      { text: "The miracle isn't that I finished. The miracle is that I had the courage to start.", author: "John Bingham" },
      { text: "Your mind is your strongest muscle.", author: "Tunde Oyeneyin" },
      { text: "Don't dream of winning, train for it!", author: "Mo Farah" },
      { text: "Fight fatigue with focus.", author: "Andy Speer" },
      { text: "Running is the greatest metaphor for life, because you get out of it what you put into it.", author: "Oprah Winfrey" }
    ];

    const startBtn = document.getElementById('startBtn');
    const againBtn = document.getElementById('againBtn');
    const gifContainer = document.getElementById('gifContainer');
    const quoteBox = document.getElementById('quoteBox');
    const quoteText = document.getElementById('quote');
    const authorText = document.getElementById('author');
    const title = document.getElementById('title');

    function showRandomQuote() {
      const random = QUOTES[Math.floor(Math.random() * QUOTES.length)];
      quoteText.textContent = '"' + random.text + '"';
      authorText.textContent = '- ' + random.author;
    }

    startBtn.addEventListener('click', () => {
      startBtn.style.display = 'none';
      title.style.display = 'none';
      gifContainer.style.display = 'block';

      setTimeout(() => {
        gifContainer.style.display = 'none';
        showRandomQuote();
        quoteBox.style.display = 'block';
      }, 2500);
    });

    againBtn.addEventListener('click', () => {
      quoteBox.style.display = 'none';
      gifContainer.style.display = 'block';

      setTimeout(() => {
        gifContainer.style.display = 'none';
        showRandomQuote();
        quoteBox.style.display = 'block';
      }, 2500);
    });
  </script>
</body>
</html>
```
