<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>LED Kedap-Kedip</title>
  <style>
    body {
      background-color: #111;
      color: #fff;
      text-align: center;
      font-family: Arial, sans-serif;
      margin-top: 100px;
    }

    .led {
      width: 100px;
      height: 100px;
      margin: auto;
      border-radius: 50%;
      background-color: #444;
      box-shadow: 0 0 10px #000;
      transition: background-color 0.3s, box-shadow 0.3s;
    }

    .led.on {
      background-color: yellow;
      box-shadow: 0 0 40px yellow;
    }

    .button {
      margin-top: 30px;
      padding: 10px 25px;
      font-size: 1em;
      background-color: #ffc107;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }

    h1 {
      margin-top: 40px;
    }
  </style>
</head>
<body>
  <div class="led" id="led"></div>
  <h1>Simulasi LED Kedap-Kedip 💡</h1>
  <button class="button" onclick="toggle()">▶️ Start / ⏸️ Stop</button>

  <script>
    const led = document.getElementById("led");
    let blinking = false;
    let interval;

    function toggle() {
      blinking = !blinking;
      if (blinking) {
        interval = setInterval(() => {
          led.classList.toggle("on");
        }, 500);
      } else {
        clearInterval(interval);
        led.classList.remove("on");
      }
    }
  </script>
</body>
</html>
