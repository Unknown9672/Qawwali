<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Qawwali</title>

  <style>
    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      font-family: Arial, sans-serif;
      background: white;
      color: black;
    }

    button {
      width: 85%;
      max-width: 360px;
      height: 130px;
      border: 2px solid black;
      border-radius: 22px;
      background: white;
      color: black;
      font-size: 28px;
      font-weight: bold;
      cursor: pointer;
    }

    button:active {
      transform: scale(0.97);
    }

    #msg {
      margin-top: 18px;
      font-size: 15px;
    }
  </style>
</head>

<body>
  <div>
    <h1>🎵 QAWALI</h1>

    <button onclick="playSound()">▶ PLAY QAWALI</button>

    <p id="msg">Tap the button to play</p>
  </div>

  <audio id="sound" preload="auto">
    <source src="don%27t%20play%20ah.mp3" type="audio/mpeg">
  </audio>

  <script>
    function playSound() {
      const sound = document.getElementById("sound");
      const msg = document.getElementById("msg");

      sound.currentTime = 0;

      sound.play()
        .then(() => {
          msg.innerHTML = "🎶 Playing...";
        })
        .catch(() => {
          msg.innerHTML = "Sound file not found";
        });
    }
  </script>
</body>
</html>
