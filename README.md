<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Daan Tech DOCS</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
:root { --green:#00ff66; --black:#000; }

* {
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:"Courier New", monospace;
}

body {
  background:var(--black);
  color:var(--green);
  padding:24px;
  overflow-x:hidden;
}

/* MATRIX RAIN */
#matrix {
  position:fixed;
  inset:0;
  z-index:-1;
}

/* HEADER */
header {
  border-bottom:1px solid var(--green);
  margin-bottom:32px;
  padding-bottom:12px;
  display:flex;
  justify-content:space-between;
  align-items:center;
}

header h1 { cursor:pointer; }

/* NAV BAR */
nav {
  background:black;
  border:1px solid var(--green);
  padding:6px 12px;
  display:flex;
  align-items:center;
}

nav a {
  color:var(--green);
  margin-left:16px;
  text-decoration:none;
  cursor:pointer;
}

nav a:first-child { margin-left:0; }
nav a:hover { text-decoration:underline; }

/* PAGES */
.page {
  display:none;
  border:1px solid var(--green);
  padding:24px;
  white-space:pre-line;
  background:rgba(0,0,0,0.85);
  position:relative;
}

.page.active { display:block; }

/* PROJECTS */
.project-grid {
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
  gap:20px;
  margin-top:20px;
}

.project-button {
  border:1px solid var(--green);
  padding:16px;
  cursor:pointer;
}

.project-button:hover {
  background:rgba(0,255,102,.08);
}

/* PROJECTS ASCII */
.projects-ascii {
  position:absolute;
  top:-1px;
  right:-1px;
  font-size:10px;
  line-height:10px;
  opacity:0.85;
  pointer-events:none;
}

/* PROJECT OVERLAY */
.overlay {
  position:fixed;
  inset:0;
  display:none;
  align-items:center;
  justify-content:center;
  z-index:100;
  background:transparent;
}

.tab {
  width:90%;
  max-width:900px;
  max-height:90vh;
  overflow-y:auto;
  border:1px solid var(--green);
  padding:24px;
  position:relative;
  background:black;
}

.close-btn {
  position:absolute;
  top:10px;
  right:10px;
  border:1px solid var(--green);
  width:28px;
  height:28px;
  display:flex;
  align-items:center;
  justify-content:center;
  cursor:pointer;
}

.close-btn:hover {
  background:rgba(0,255,102,.1);
}

a.link {
  color:var(--green);
  text-decoration:underline;
}

table {
  border-collapse:collapse;
  margin:12px 0;
  width:100%;
}

td, th {
  border:1px solid var(--green);
  padding:6px 10px;
}

/* CURSOR */
.cursor {
  display:inline-block;
  width:10px;
  height:1em;
  background:var(--green);
  margin-left:4px;
  animation:blink 1s steps(1) infinite;
}

@keyframes blink { 50% { opacity:0; } }

/* ERROR POPUP */
#errorPopup {
  position:fixed;
  inset:0;
  display:none;
  align-items:center;
  justify-content:center;
  z-index:200;
  pointer-events:none;
}

#errorBox {
  width:520px;
  background:black;
  border:2px solid var(--green);
}

#errorTop {
  display:flex;
  justify-content:space-between;
  align-items:center;
  padding:6px 10px;
  border-bottom:2px solid var(--green);
}

#errorClose {
  cursor:pointer;
  padding:2px 8px;
  border:1px solid var(--green);
}

#errorClose:hover {
  background:rgba(0,255,102,.15);
}

#errorBody {
  padding:24px 20px;
  text-align:center;
  line-height:1.6;
}

footer {
  margin-top:32px;
  opacity:.7;
}
</style>
</head>

<body>

<canvas id="matrix"></canvas>

<header>
  <h1 onclick="showPage('home')">Daan Tech DOCS</h1>
  <nav>
    <a onclick="showPage('home')">HOME</a>
    <a onclick="showPage('about')">ABOUT</a>
    <a onclick="showPage('projects')">PROJECTS</a>
    <a onclick="showPage('contact')">CONTACT</a>
    <a onclick="showPage('help')">HELP</a>
  </nav>
</header>

<!-- HOME -->
<div id="home" class="page active">
<pre>
         /$$                                     /$$                         /$$         /$$  
       | $$                                    | $$                        | $$       /$$$$  
   /$$$$$$$  /$$$$$$   /$$$$$$  /$$$$$$$      /$$$$$$    /$$$$$$   /$$$$$$$| $$$$$$$ |_  $$  
  /$$__  $$ |____  $$ |____  $$| $$__  $$    |_  $$_/   /$$__  $$ /$$_____/| $$__  $$  | $$  
 | $$  | $$  /$$$$$$$  /$$$$$$$| $$  \ $$      | $$    | $$$$$$$$| $$      | $$  \ $$  | $$  
 | $$  | $$ /$$__  $$ /$$__  $$| $$  | $$      | $$ /$$| $$_____/| $$      | $$  | $$  | $$  
 |  $$$$$$$|  $$$$$$$|  $$$$$$$| $$  | $$      |  $$$$/|  $$$$$$$|  $$$$$$$| $$  | $$ /$$$$$$
  \_______/ \_______/ \_______/|__/  |__//$$$$$$\___/   \_______/ \_______/|__/  |__/|______/
                                        |______/
</pre>

Welcome to the official Daan Tech DOCS website.

This website is created and designed by Daan Tech and serves as the central
documentation hub for nearly all of my projects.

SYSTEM STATUS: <span id="status"></span><span class="cursor"></span>
</div>

<!-- ABOUT -->
<div id="about" class="page">
ABOUT Daan Tech

Daan Tech focuses on hardware experimentation, embedded systems,
wireless research, and technical projects.

I also developed a Roblox roleplay game based on the classic
Dutch television series "Flodder".

Roblox Flodder RP:
https://www.roblox.com/games/132182877945966/Roblox-Flodder-RP

<pre>
 _______________________
|                       | _ __
|     @daan_tech1       ||=|##L_
|________________.====._||_|__._]
 `(_)(_)`       `(_)(_)"""="=(_)
</pre>
</div>

<!-- PROJECTS -->
<div id="projects" class="page">
PROJECTS

<pre class="projects-ascii">
      ____
 ____|    \
(____|     `.________________________
 ____|       _|______________________
(____|     .'
     |____/
</pre>

<div class="project-grid">
  <div class="project-button" onclick="openProject('jammer')">
    01. ESP32-C3 Super Mini Jammer
  </div>
  <div class="project-button" onclick="openProject('matrix')">
    02. WiFi 8x8 Matrix Panel
  </div>
  <div class="project-button" onclick="openProject('tesla')">
    03. Arduino Nano CC1101 Tesla Charging Port Opener
  </div>
</div>
</div>

<!-- CONTACT -->
<div id="contact" class="page">
CONTACT

If you have any questions, feel free to contact me.

Twitch     \
YouTube ----  @daan_tech1
TikTok     /

Mail:
business.daantech@gmail.com
</div>

<!-- HELP -->
<div id="help" class="page">
HELP

This content is provided for educational and experimental purposes.
</div>

<!-- PROJECT WINDOW (POPUP TAB) -->
<div class="overlay" id="overlay">
  <div class="tab">
    <div class="close-btn" onclick="closeProject()">X</div>

    <h2 id="projTitle"></h2>
    <div id="projDesc"></div>

    <p>
      Source code:<br>
      <a id="projLink" class="link" href="#" target="_blank">View on GitHub</a>
    </p>
  </div>
</div>

<!-- ERROR POPUP -->
<div id="errorPopup">
  <div id="errorBox">
    <div id="errorTop">
      <span>ERROR</span>
      <span id="errorClose" onclick="closeError()">X</span>
    </div>
    <div id="errorBody">
      DO YOU ALREADY<br>
      FOLLOW @daan_tech1<br>
      ON YOUTUBE?
    </div>
  </div>
</div>

<footer>
© 2026 Daan Tech — Terminal Interface
</footer>

<script>
/* PAGE NAV */
function showPage(id) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  const el = document.getElementById(id);
  if (el) el.classList.add('active');
}

/* PROJECT DATA */
const projects = {
  jammer: {
    title: "01. ESP32-C3 Super Mini Jammer",
    desc: `
<p>ESP32-C3 based experimental wireless project for educational and research purposes.</p>

<h3>Pin Connections</h3>
<table>
<tr><th>ESP32-C3</th><th>NRF24</th></tr>
<tr><td>GPIO 4</td><td>SCK</td></tr>
<tr><td>GPIO 5</td><td>MISO</td></tr>
<tr><td>GPIO 6</td><td>MOSI</td></tr>
<tr><td>GPIO 20</td><td>CE</td></tr>
<tr><td>GPIO 21</td><td>CSN</td></tr>
</table>
`,
    link: "https://github.com/daantech1/esp32-c3-jammer/blob/main/ESP32C3superminijammer.ino"
  },
  matrix: {
    title: "02. WiFi 8x8 Matrix Panel",
    desc: `
<p>ESP32 powered dual 8x8 LED matrix panel with WiFi AP, web interface, NTP time sync and scrolling text.</p>

<h3>Pin Connections</h3>
<table>
<tr><th>ESP32</th><th>Matrix</th></tr>
<tr><td>GPIO 23</td><td>DIN</td></tr>
<tr><td>GPIO 18</td><td>CLK</td></tr>
<tr><td>GPIO 5</td><td>CS1 (left)</td></tr>
<tr><td>GPIO 4</td><td>CS2 (right)</td></tr>
</table>
`,
    link: "https://github.com/daantech1/esp32-8x8-matrix-wifi-panel/blob/main/sour_apple_esp32.ino"
  },
  tesla: {
    title: "03. Arduino Nano CC1101 Tesla Charging Port Opener",
    desc: `
<p>This file is made for Arduino NANO, it will power a CC1101 to open a Tesla charging port.</p>

<h3>Pin Connections</h3>
<table>
<tr><th>Arduino Nano</th><th>CC1101</th></tr>
<tr><td>D2</td><td>GDO0</td></tr>
<tr><td>D3</td><td>GDO2</td></tr>
<tr><td>D10</td><td>CSN/CS</td></tr>
<tr><td>D11</td><td>MOSI</td></tr>
<tr><td>D12</td><td>MISO</td></tr>
<tr><td>D13</td><td>SCK</td></tr>
<tr><td>3.3V</td><td>VCC (do NOT use 5V)</td></tr>
<tr><td>GND</td><td>GND</td></tr>
<tr><td>3.3V</td><td>VCO/VCC_RF (if present)</td></tr>
</table>
`,
    link: "https://github.com/daantech1/arduino-nano-cc1101-Tesla-charging-port-opener/blob/main/EU_T_opener_ArduinoNano_CC1101"
  }
};

function openProject(key) {
  document.getElementById("projTitle").innerText = projects[key].title;
  document.getElementById("projDesc").innerHTML = projects[key].desc;
  document.getElementById("projLink").href = projects[key].link;
  document.getElementById("overlay").style.display = "flex";
}

function closeProject() {
  document.getElementById("overlay").style.display = "none";
}

/* STATUS TYPING */
const statusEl = document.getElementById("status");
const word = "ONLINE";
let idx = 0;
let typing = true;

(function typeLoop() {
  if (typing) {
    if (idx < word.length) {
      statusEl.textContent += word.charAt(idx);
      idx++;
    } else {
      setTimeout(() => typing = false, 1200);
    }
  } else {
    if (idx > 0) {
      statusEl.textContent = statusEl.textContent.slice(0, -1);
      idx--;
    } else {
      setTimeout(() => typing = true, 800);
    }
  }
  setTimeout(typeLoop, typing ? 120 : 80);
})();

/* ERROR POPUP TIMER */
setTimeout(() => {
  const p = document.getElementById("errorPopup");
  p.style.display = "flex";
  p.style.pointerEvents = "auto";
}, 30000);

function closeError() {
  const p = document.getElementById("errorPopup");
  p.style.display = "none";
  p.style.pointerEvents = "none";
}

/* MATRIX RAIN */
const canvas = document.getElementById("matrix");
const ctx = canvas.getContext("2d");

function resize() {
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;
}
resize();
window.addEventListener("resize", resize);

const letters = "01ABCDEFGHIJKLMNOPQRSTUVWXYZ@#$%";
const fontSize = 14;

function resetDrops() {
  const columns = Math.floor(canvas.width / fontSize);
  return Array(columns).fill(1);
}

let drops = resetDrops();
window.addEventListener("resize", () => { drops = resetDrops(); });

setInterval(() => {
  ctx.fillStyle = "rgba(0,0,0,0.05)";
  ctx.fillRect(0, 0, canvas.width, canvas.height);

  ctx.fillStyle = "#00ff66";
  ctx.font = fontSize + "px monospace";

  for (let i = 0; i < drops.length; i++) {
    const char = letters[Math.floor(Math.random() * letters.length)];
    ctx.fillText(char, i * fontSize, drops[i] * fontSize);

    if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
      drops[i] = 0;
    }
    drops[i]++;
  }
}, 33);
</script>

</body>
</html>
