<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Happy Friendship Day!</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background: linear-gradient(to right, #ffecd2, #fcb69f);
      overflow-x: hidden;
    }

    #header {
      text-align: center;
      padding: 100px 20px 40px;
      font-size: 40px;
      color: #800000;
      animation: fadeIn 2s ease-in-out;
    }

    #surpriseBtn {
      display: block;
      margin: 0 auto;
      padding: 15px 30px;
      font-size: 22px;
      background-color: #ff69b4;
      color: white;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      animation: pulse 2s infinite;
    }

    #message {
      display: none;
      text-align: center;
      margin-top: 50px;
      font-size: 26px;
      color: #5d005d;
      white-space: pre-line;
      padding: 0 20px;
    }

    .emoji {
      font-size: 40px;
      animation: float 4s linear infinite;
      position: absolute;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(-30px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.1); }
      100% { transform: scale(1); }
    }

    @keyframes float {
      0% { top: 100%; opacity: 1; }
      100% { top: -10%; opacity: 0; }
    }
  </style>
</head>
<body>

  <div id="header">🎉 Happy Friendship Day! 🎉</div>
  <button id="surpriseBtn">Click to reveal a secret message 🎁</button>

  <div id="message">
    You're the kind of friend who makes life sparkle! ✨

    Thank you for your laughter, your kindness, and your friendship.

    Today is for YOU. 🌟

    Let’s celebrate the bond that never fades! 🧡🎈
  </div>

  <script>
    const btn = document.getElementById('surpriseBtn');
    const msg = document.getElementById('message');

    btn.addEventListener('click', () => {
      msg.style.display = 'block';
      createEmojis();
      btn.style.display = 'none';
    });

    function createEmojis() {
      const emojis = ['💛','💖','💫','🎉','🌟','🧡'];
      for (let i = 0; i < 30; i++) {
        const emoji = document.createElement('div');
        emoji.classList.add('emoji');
        emoji.textContent = emojis[Math.floor(Math.random() * emojis.length)];
        emoji.style.left = Math.random() * 100 + 'vw';
        emoji.style.animationDuration = (3 + Math.random() * 2) + 's';
        document.body.appendChild(emoji);

        setTimeout(() => emoji.remove(), 6000);
      }
    }
  </script>

</body>
</html>
