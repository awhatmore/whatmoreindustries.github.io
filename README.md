
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
      line-height: 1.6;
    }

    #particles-js {
      position: fixed;
      width: 100%;
      height: 100%;
      z-index: -1;
    }

    header {
      background: transparent;
      text-align: center;
      padding: 3rem 1rem 2rem;
      z-index: 1;
      position: relative;
    }

    header h1 {
      font-size: 1.6rem;
      margin: 0;
    }

    header p {
      font-size: 1.0rem;
      color: #aaa;
      margin-top: 0.5rem;
    }

    nav {
      display: flex;
      justify-content: center;
      gap: 2rem;
      background: rgba(34, 34, 34, 0.9);
      padding: 1rem;
      position: sticky;
      top: 0;
      z-index: 10;
    }

    nav a {
      color: #fff;
      text-decoration: none;
    }

    nav a:hover {
      text-decoration: underline;
    }

    main {
      padding: 2rem 1rem;
      max-width: 800px;
      margin: auto;
      position: relative;
      z-index: 1;
    }

    section {
      margin-bottom: 3rem;
    }

    footer {
      background: #1e1e1e;
      text-align: center;
      padding: 1rem;
      font-size: 0.9rem;
      color: #666;
    }

    a {
      color: #00ffff;
    }

    @media (max-width: 600px) {
      header h1 { font-size: 2rem; }
      nav { flex-wrap: wrap; gap: 1rem; }
    }
  </style>
</head>
<body>
  <div id="particles-js"></div>

  <header>
    <h1>WHATMORE INDUSTRIES</h1>
    <p>"A Living Archive: A Mind in Motion."</p>
  </header>

  <nav>
    <a href="#about">About</a>
    <a href="#projects">Projects</a>
    <a href="#journal">Journal</a>
    <a href="#contact">Contact</a>
  </nav>
  
  <section id="calculator">
  <h2>Smart Unit Calculator</h2>
  <div style="background:#222; padding:1rem; border-radius:0.5rem; font-size:1rem;">
    <div id="display" style="background:#000; padding:0.5rem 1rem; margin-bottom:1rem; color:#0f0; font-weight:bold;">
      0
    </div>

    <div style="display: flex; flex-wrap: wrap; gap: 0.5rem;">
      <!-- Number buttons -->
      ${[1,2,3,4,5,6,7,8,9,0,'.'].map(n =>
        `<button onclick="appendCalc('${n}')">${n}</button>`).join('')}
      <button onclick="clearCalc()">Clear</button>
      <button onclick="backspace()">←</button>
      <button onclick="calculate()">=</button>
    </div><br>

    <!-- Operation buttons -->
    <div>
      <button onclick="appendCalc(' + ')">+</button>
      <button onclick="appendCalc(' - ')">-</button>
      <button onclick="appendCalc(' * ')">*</button>
      <button onclick="appendCalc(' / ')">/</button>
    </div><br>

    <!-- Length Units -->
    <div>
      <strong>Length</strong><br>
      ${['nm','μm','mm','cm','m','km','in','ft','yd','mi'].map(u =>
        `<button onclick="appendCalc(' ${u} ')">${u}</button>`).join('')}
    </div><br>

    <!-- Mass Units -->
    <div>
      <strong>Mass</strong><br>
      ${['mg','g','kg','t','oz','lb','st'].map(u =>
        `<button onclick="appendCalc(' ${u} ')">${u}</button>`).join('')}
    </div><br>

    <!-- Time Units -->
    <div>
      <strong>Time</strong><br>
      ${['ns','μs','ms','s','min','hr','day'].map(u =>
        `<button onclick="appendCalc(' ${u} ')">${u}</button>`).join('')}
    </div>
  </div>
</section>

  <main>
    <section id="about">
      <h2>About</h2>
      <p>I am the founder of Whatmore Industries. I build, test, observe, and connect — from off-grid systems and theoretical models to hands-on fabrication and prototyping. Every line I draw and every circuit I etch aims to serve a greater curiosity: what more is possible?</p>
    </section>

    <section id="projects">
      <h2>Projects</h2>
      <p>Explore my work in electromaterials, antenna theory, sustainable design, and beyond. Each project is a story of purpose and discovery.</p>
    </section>

    <section id="journal">
      <h2>Journal</h2>
      <p>Thoughts, theories, and breakthroughs — documented in motion. This is where process meets philosophy.</p>
    </section>

    <section id="contact">
      <h2>Contact</h2>
      <p>To collaborate, ask questions, or propose a mission — reach out directly at <a href="mailto:contact@whatmoreindustries.io">contact@whatmoreindustries.io</a>.</p>
    </section>
  </main>

  <footer>
    &copy; 2025 Whatmore Industries. All rights reserved.
  </footer>

  <!-- Particles.js -->
  <script src="https://cdn.jsdelivr.net/npm/particles.js@2.0.0/particles.min.js"></script>
  <script>
    particlesJS("particles-js", {
      particles: {
        number: { value: 80, density: { enable: true, value_area: 800 }},
        color: { value: "#00ffff" },
        shape: { type: "circle" },
        opacity: { value: 0.5 },
        size: { value: 3, random: true },
        line_linked: {
          enable: true,
          distance: 150,
          color: "#00ffff",
          opacity: 0.4,
          width: 1
        },
        move: {
          enable: true,
          speed: 2,
          direction: "none"
        }
      },
      interactivity: {
        events: {
          onhover: { enable: true, mode: "repulse" },
          onclick: { enable: true, mode: "push" }
        },
        modes: {
          repulse: { distance: 100, duration: 0.4 },
          push: { particles_nb: 4 }
        }
      },
      retina_detect: true
    });
  </script>
  
  <script>
  <script>
  let currentCalc = '';

  function appendCalc(str) {
    currentCalc += str;
    document.getElementById('display').textContent = currentCalc;
  }

  function clearCalc() {
    currentCalc = '';
    document.getElementById('display').textContent = '0';
  }

  function backspace() {
    currentCalc = currentCalc.trim().slice(0, -1);
    document.getElementById('display').textContent = currentCalc || '0';
  }

  function calculate() {
    try {
      // TODO: parse units and do conversions before eval
      const result = eval(currentCalc.replace(/[a-zA-Z]+/g, ''));
      document.getElementById('display').textContent = result.toFixed(4);
      currentCalc = result.toString();
    } catch (e) {
      document.getElementById('display').textContent = 'Error';
    }
  }
</script>
</body>
</html>


