<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>For Hachikaru 💜</title>
  <style>
    body {
      background: linear-gradient(135deg, #7f5af0, #c77dff);
      font-family: 'Segoe UI', sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      overflow: hidden;
      color: #333;
    }

    .card {
      background: #ffffff;
      padding: 35px;
      border-radius: 25px;
      max-width: 420px;
      text-align: center;
      box-shadow: 0 15px 40px rgba(0,0,0,0.25);
      z-index: 2;
    }

    h1, h2 {
      color: #7f5af0;
    }

    p {
      font-size: 16px;
      line-height: 1.6;
    }

    button {
      margin-top: 15px;
      padding: 12px 24px;
      font-size: 16px;
      border: none;
      border-radius: 30px;
      cursor: pointer;
    }

    .yes {
      background: #7f5af0;
      color: white;
      animation: pulse 1.8s infinite;
    }

    .maybe {
      background: #eee;
    }

    .footer {
      margin-top: 20px;
      font-size: 13px;
      color: #777;
    }

    /* Pulse animation */
    @keyframes pulse {
      0% { transform: scale(1); box-shadow: 0 0 0 0 rgba(127,90,240,.6); }
      70% { transform: scale(1.05); box-shadow: 0 0 0 14px rgba(127,90,240,0); }
      100% { transform: scale(1); }
    }

    /* Floating hearts */
    .heart {
      position: absolute;
      bottom: -20px;
      font-size: 20px;
      animation: float 6s linear infinite;
      opacity: 0.6;
      color: #c77dff;
    }

    @keyframes float {
      0% { transform: translateY(0); opacity: 0; }
      20% { opacity: 0.6; }
      100% { transform: translateY(-110vh); opacity: 0; }
    }

    .hidden {
      display: none;
    }
  </style>
</head>
<body onclick="playMusic()">

  <!-- Background Music -->
  <audio id="music" loop>
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
  </audio>

  <!-- Page 1 -->
  <div class="card" id="page1">
    <h1>Hey Hachikaru 💜</h1>

    <p>
      I’ve known you for about three years now, and over that time,
      you’ve slowly become someone I genuinely care about.
    </p>

    <p>
      Being around you feels easy and natural.
      You have this calm way of making moments feel lighter,
      and I really appreciate that about you.
    </p>

    <p>
      I didn’t want to rush this or keep it unsaid anymore.
      I just wanted to be honest with you and with myself.
    </p>

    <h2>Will you be my girlfriend? 💕</h2>

    <button class="yes" onclick="yesClicked(event)">Yes 💜</button>
    <button class="maybe" onclick="alert('That’s completely okay 💜 Take all the time you need 😊')">
      Think about it 🤍
    </button>

    <div class="footer">— Runo 💜</div>
  </div>

  <!-- Page 2 -->
  <div class="card hidden" id="page2">
    <h1>Thank you 💜</h1>
    <p>
      No matter your answer, I’m really glad you took the time to read this.
    </p>
    <p>
      You truly matter to me, Hachikaru.
    </p>
    <h2>💜</h2>
    <div class="footer">— Runo</div>
  </div>

  <script>
    // Floating hearts
    setInterval(() => {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerHTML = "💜";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.fontSize = (14 + Math.random() * 20) + "px";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 6000);
    }, 500);

    // Music play (mobile-friendly)
    function playMusic() {
      const music = document.getElementById("music");
      if (music.paused) music.play();
    }

    // Yes button action
    function yesClicked(event) {
      event.stopPropagation();
      document.getElementById("page1").classList.add("hidden");
      document.getElementById("page2").classList.remove("hidden");
    }
  </script>

</body>
</html># hachikaru
