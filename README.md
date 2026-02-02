# Valentinee
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Valentine 💘</title>
  <style>
    body {
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: Arial, sans-serif;
      overflow: hidden;
    }

    .container {
      text-align: center;
      z-index: 2;
    }

    h1 {
      font-size: 3em;
      color: white;
      margin-bottom: 40px;
      animation: shake 2s infinite;
    }

    @keyframes shake {
      0% { transform: translate(0, 0); }
      25% { transform: translate(5px, -5px); }
      50% { transform: translate(-5px, 5px); }
      75% { transform: translate(5px, 5px); }
      100% { transform: translate(0, 0); }
    }

    button {
      font-size: 1.5em;
      padding: 15px 40px;
      border-radius: 50px;
      border: none;
      cursor: pointer;
      margin: 20px;
    }

    #yes {
      background-color: #ff4d6d;
      color: white;
    }

    #no {
      background-color: white;
      color: #ff4d6d;
      position: absolute;
    }

    #message {
      font-size: 2em;
      color: white;
      margin-top: 20px;
      display: none;
    }

    #date {
      font-size: 1.6em;
      color: white;
      margin-top: 10px;
      display: none;
    }

    .heart {
      position: fixed;
      top: -20px;
      font-size: 24px;
      animation: fall linear forwards;
      color: red;
      z-index: 1;
    }

    @keyframes fall {
      to {
        transform: translateY(110vh);
        opacity: 0;
      }
    }

    iframe {
      display: none;
    }
  </style>
</head>
<body>

  <div class="container">
    <h1>Marlène, veux-tu être ma Valentine ? 💘</h1>
    <button id="yes">OUI 💖</button>
    <button id="no">NON 💔</button>
    <div id="message">Je savais que tu dirais oui Marlène 💕😍</div>
    <div id="date">Rendez-vous le 13 février à 22h 😘</div>
  </div>

  <iframe id="music" src="" allow="autoplay"></iframe>

  <script>
    const noButton = document.getElementById("no");
    const yesButton = document.getElementById("yes");
    const message = document.getElementById("message");
    const date = document.getElementById("date");
    const music = document.getElementById("music");

    noButton.addEventListener("mouseover", () => {
      const x = Math.random() * (window.innerWidth - noButton.clientWidth);
      const y = Math.random() * (window.innerHeight - noButton.clientHeight);
      noButton.style.left = x + "px";
      noButton.style.top = y + "px";
    });

    yesButton.addEventListener("click", () => {
      yesButton.style.display = "none";
      noButton.style.display = "none";
      message.style.display = "block";
      date.style.display = "block";

      music.src = "https://www.youtube.com/embed/6G90ZcmZpAI?autoplay=1";

      setInterval(createHeart, 300);
    });

    function createHeart() {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.innerHTML = "❤️";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = Math.random() * 2 + 3 + "s";
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 5000);
    }
  </script>

</body>
</html>
