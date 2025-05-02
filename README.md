<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Whatmore Industries</title>
  <style>
    html, body {
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', sans-serif;
      background: #111;
      color: #eee;
      height: 100%;
      overflow: hidden;
    }
    #particles-js {
      position: fixed;
      width: 100%;
      height: 100%;
      z-index: -1;
    }
    .content {
      position: relative;
      z-index: 1;
      text-align: center;
      padding-top: 20vh;
    }
    h1 {
      font-size: 3rem;
      margin-bottom: 0.5rem;
    }
    p {
      font-size: 1.25rem;
      max-width: 600px;
      margin: 0 auto;
      line-height: 1.6;
    }
  </style>
</head>
<body>
  <div id="particles-js"></div>
  <div class="content">
    <h1>WHATMORE INDUSTRIES</h1>
    <p>"A Living Archive. A Mind in Motion." Exploring energy, fabric, resonance, and invention across dimensions.</p>
  </div>

  <!-- Particles.js -->
  <script src="https://cdn.jsdelivr.net/npm/particles.js@2.0.0/particles.min.js"></script>
  <script>
    particlesJS("particles-js", {
      "particles": {
        "number": {
          "value": 80,
          "density": {
            "enable": true,
            "value_area": 800
          }
        },
        "color": { "value": "#00ffff" },
        "shape": {
          "type": "circle",
          "stroke": { "width": 0, "color": "#000000" }
        },
        "opacity": {
          "value": 0.5,
          "random": false
        },
        "size": {
          "value": 3,
          "random": true
        },
        "line_linked": {
          "enable": true,
          "distance": 150,
          "color": "#00ffff",
          "opacity": 0.4,
          "width": 1
        },
        "move": {
          "enable": true,
          "speed": 2,
          "direction": "none",
          "random": false,
          "straight": false,
          "bounce": false
        }
      },
      "interactivity": {
        "detect_on": "canvas",
        "events": {
          "onhover": { "enable": true, "mode": "repulse" },
          "onclick": { "enable": true, "mode": "push" }
        },
        "modes": {
          "repulse": { "distance": 100, "duration": 0.4 },
          "push": { "particles_nb": 4 }
        }
      },
      "retina_detect": true
    });
  </script>
</body>
</html>
