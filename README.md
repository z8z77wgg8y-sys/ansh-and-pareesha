<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>A Special Question for Parisha ✨</title>
  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@400;600;700&family=Nunito:wght@400;700&display=swap" rel="stylesheet">
  
  <style>
    :root {
      --bg-color: #fff5f7;
      --primary: #ff4b72;
      --secondary: #ff85a1;
      --accent: #ffd1dc;
      --text: #4a3e3d;
      --card-bg: #ffffff;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Nunito', sans-serif;
      background-color: var(--bg-color);
      color: var(--text);
      overflow-x: hidden;
      padding-bottom: 50px;
    }

    /* Floating Heart Background Animation */
    .heart-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 0;
      overflow: hidden;
    }

    .floating-heart {
      position: absolute;
      font-size: 1.5rem;
      animation: floatUp 8s linear infinite;
      opacity: 0.6;
    }

    @keyframes floatUp {
      0% { transform: translateY(100vh) rotate(0deg); opacity: 0.8; }
      100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
    }

    /* Container & Layout */
    .container {
      max-width: 700px;
      margin: 0 auto;
      padding: 20px;
      position: relative;
      z-index: 1;
      text-align: center;
    }

    header {
      margin-top: 30px;
      margin-bottom: 30px;
    }

    h1, h2, h3 {
      font-family: 'Fredoka', sans-serif;
    }

    .badge {
      display: inline-block;
      background-color: #ffe0e6;
      color: var(--primary);
      padding: 6px 16px;
      border-radius: 20px;
      font-weight: 700;
      font-size: 0.9rem;
      margin-bottom: 12px;
      border: 1px dashed var(--primary);
    }

    h1 {
      color: var(--primary);
      font-size: 2.2rem;
      margin-bottom: 8px;
    }

    .subtitle {
      font-size: 1.1rem;
      color: #776063;
    }

    /* Music Box */
    .music-card {
      background: var(--card-bg);
      border-radius: 16px;
      padding: 15px;
      margin-bottom: 30px;
      box-shadow: 0 8px 20px rgba(255, 133, 161, 0.15);
      border: 2px solid var(--accent);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 10px;
    }

    .music-card p {
      font-weight: 700;
      color: var(--primary);
      font-size: 0.95rem;
    }

    audio {
      width: 100%;
      max-width: 350px;
      height: 40px;
    }

    /* Evidence Cards */
    .section-title {
      color: var(--primary);
      font-size: 1.6rem;
      margin: 30px 0 20px;
    }

    .cards-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 18px;
    }

    .card {
      background: var(--card-bg);
      padding: 20px;
      border-radius: 16px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.04);
      text-align: left;
      border-left: 5px solid var(--secondary);
      transition: transform 0.2s;
    }

    .card:hover {
      transform: translateY(-3px);
    }

    .card-icon {
      font-size: 1.8rem;
      margin-bottom: 8px;
    }

    .card h3 {
      color: var(--primary);
      font-size: 1.2rem;
      margin-bottom: 6px;
    }

    .card p {
      font-size: 0.98rem;
      line-height: 1.5;
      color: #5a4b4d;
    }

    /* Note Card */
    .note-card {
      background: #fff0f3;
      border: 2px dashed var(--primary);
      border-radius: 16px;
      padding: 25px;
      margin: 35px 0;
      text-align: center;
    }

    .note-card p {
      font-size: 1.05rem;
      line-height: 1.6;
      color: #4a3e3d;
      font-style: italic;
    }

    /* Proposal Arena */
    .proposal-box {
      background: var(--card-bg);
      padding: 40px 20px;
      border-radius: 24px;
      box-shadow: 0 10px 30px rgba(255, 75, 114, 0.2);
      border: 3px solid var(--secondary);
      position: relative;
      min-height: 260px;
    }

    .proposal-box h2 {
      font-size: 1.8rem;
      color: var(--primary);
      margin-bottom: 25px;
    }

    .btn-group {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 20px;
      position: relative;
      min-height: 80px;
    }

    button {
      font-family: 'Fredoka', sans-serif;
      font-size: 1.2rem;
      padding: 12px 32px;
      border-radius: 50px;
      border: none;
      cursor: pointer;
      transition: all 0.2s ease;
    }

    #yesBtn {
      background-color: var(--primary);
      color: white;
      box-shadow: 0 4px 15px rgba(255, 75, 114, 0.4);
    }

    #yesBtn:hover {
      transform: scale(1.1);
      background-color: #e03a5f;
    }

    #noBtn {
      background-color: #e2e8f0;
      color: #64748b;
      position: absolute;
      z-index: 10;
    }

    /* Victory Message */
    #celebration {
      display: none;
      animation: fadeIn 0.5s ease-in;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.9); }
      to { opacity: 1; transform: scale(1); }
    }

    .celebration-title {
      font-size: 2.2rem;
      color: var(--primary);
      margin-bottom: 15px;
    }

    .celebration-text {
      font-size: 1.2rem;
      line-height: 1.6;
    }
  </style>
</head>
<body>

  <!-- Floating Hearts Container -->
  <div class="heart-bg" id="heartBg"></div>

  <div class="container">
    
    <header>
      <div class="badge">⚠️ OFFICIAL DOSSIER</div>
      <h1>Ansh & Parisha: The Unbiased Report</h1>
      <p class="subtitle">Please review the following facts carefully before proceeding.</p>
    </header>

    <!-- Song Section -->
    <div class="music-card">
      <p>🎵 Press Play for Background Vibe 🎵</p>
      <!-- REPLACE 'your-song.mp3' WITH YOUR AUDIO FILE OR LINK -->
      <audio controls loop>
        <source src="your-song.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </div>

    <!-- Evidence Cards -->
    <h2 class="section-title">Exhibits & Evidence</h2>
    <div class="cards-grid">
      
      <div class="card">
        <div class="card-icon">🧠</div>
        <h3>The Detail Listener</h3>
        <p>Ansh can talk about the most random topic for an hour, and Parisha will somehow remember every single detail. That's not just love—that's superpower-level listening.</p>
      </div>

      <div class="card">
        <div class="card-icon">📈</div>
        <h3>The Mood Restorer</h3>
        <p>Scientifically proven: 100% of bad days are instantly fixed just by being around Parisha. Her presence is designated as Ansh's safest and most comfortable place on Earth.</p>
      </div>

      <div class="card">
        <div class="card-icon">👑</div>
        <h3>Unshakeable Principles</h3>
        <p>Her culture, her values, and her standards are strictly non-negotiable. She never compromises on who she is, and that strength is something Ansh respects endlessly.</p>
      </div>

      <div class="card">
        <div class="card-icon">👗</div>
        <h3>Future World's Best Fashion Designer</h3>
        <p>Passionate, creative, and driven to conquer the fashion world. Partnering with Ansh guarantees front-row seats to every Paris Fashion Week show for life!</p>
      </div>

    </div>

    <!-- Heartfelt Note -->
    <div class="note-card">
      <p>"Parisha, I love how passionate you are about your dreams, how deeply you hold onto your values, and how effortlessly you make me feel comfortable and happy. I just love being around you."</p>
    </div>

    <!-- Proposal Box -->
    <div class="proposal-box">
      
      <div id="questionBox">
        <h2>Parisha, will you be my girlfriend? ❤️</h2>
        <div class="btn-group">
          <button id="yesBtn">YES! 🥰</button>
          <button id="noBtn">No 😜</button>
        </div>
      </div>

      <div id="celebration">
        <h2 class="celebration-title">BEST DECISION EVER! 🎉💃✨</h2>
        <p class="celebration-text">Ansh is officially the happiest guy alive right now! <br>Call or text him to claim your celebratory hug! ❤️</p>
      </div>

    </div>

  </div>

  <script>
    // Create background floating hearts
    const heartBg = document.getElementById('heartBg');
    const hearts = ['❤️', '💖', '✨', '🌸', '💕'];
    
    for (let i = 0; i < 25; i++) {
      const heart = document.createElement('div');
      heart.classList.add('floating-heart');
      heart.innerText = hearts[Math.floor(Math.random() * hearts.length)];
      heart.style.left = `${Math.random() * 100}vw`;
      heart.style.animationDuration = `${5 + Math.random() * 5}s`;
      heart.style.animationDelay = `${Math.random() * 5}s`;
      heartBg.appendChild(heart);
    }

    // Running No Button Logic
    const noBtn = document.getElementById('noBtn');
    const yesBtn = document.getElementById('yesBtn');
    const questionBox = document.getElementById('questionBox');
    const celebration = document.getElementById('celebration');

    const phrases = [
      "Nice try, world's best designer! 👗",
      "Error 404: 'No' not found! ❌",
      "Are you sure? Ansh has snacks! 🍫",
      "Wrong button! Try the red one! 😉",
      "Nice try, quick fingers! ⚡",
      "Almost got it... not! 😜"
    ];

    let phraseIndex = 0;

    function moveButton() {
      const x = Math.floor(Math.random() * (window.innerWidth - 120));
      const y = Math.floor(Math.random() * (window.innerHeight - 60));
      
      noBtn.style.position = 'fixed';
      noBtn.style.left = `${x}px`;
      noBtn.style.top = `${y}px`;
      
      noBtn.innerText = phrases[phraseIndex];
      phraseIndex = (phraseIndex + 1) % phrases.length;
    }

    // Move on hover (desktop) or touch (mobile)
    noBtn.addEventListener('mouseover', moveButton);
    noBtn.addEventListener('touchstart', (e) => {
      e.preventDefault();
      moveButton();
    });

    // Yes Button Trigger
    yesBtn.addEventListener('click', () => {
      questionBox.style.display = 'none';
      celebration.style.display = 'block';

      // Confetti Explosion
      confetti({
        particleCount: 120,
        spread: 80,
        origin: { y: 0.6 }
      });

      // Continuous heart confetti bursts
      var end = Date.now() + (3 * 1000);
      var colors = ['#ff4b72', '#ff85a1', '#ffffff'];

      (function frame() {
        confetti({
          particleCount: 3,
          angle: 60,
          spread: 55,
          origin: { x: 0 },
          colors: colors
        });
        confetti({
          particleCount: 3,
          angle: 120,
          spread: 55,
          origin: { x: 1 },
          colors: colors
        });

        if (Date.now() < end) {
          requestAnimationFrame(frame);
        }
      }());
    });
  </script>
</body>
</html>

