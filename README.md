# Xit-iOS-14-o-15
Xit para iPhone 14 /15<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>👹xit iOS 14💀</title>

<style>
body {
  margin: 0;
  height: 100vh;
  background: linear-gradient(120deg, #1e1e2f, #2b2b45);
  font-family: Arial;
  overflow: hidden;
}

/* =========================
   📌 PANEL PRINCIPAL (TU ORIGINAL)
========================= */
#panel {
  width: 240px;
  position: fixed;
  top: 120px;
  left: 20px;
  background: rgba(0,0,0,0.65);
  backdrop-filter: blur(10px);
  border-radius: 12px;
  border: 1px solid rgba(255,255,255,0.2);
  color: white;
  box-shadow: 0 10px 30px rgba(0,0,0,0.5);
}

#header {
  padding: 10px;
  text-align: center;
  font-weight: bold;
  cursor: grab;
  background: rgba(255,255,255,0.15);
  border-top-left-radius: 12px;
  border-top-right-radius: 12px;
}

/* 🌈 BOTONES PANEL */
#panel button {
  width: 90%;
  margin: 8px 10px;
  padding: 8px;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  color: yellow;
  font-weight: bold;
  animation: rainbow 4s infinite;
}

@keyframes rainbow {
  0% {background:red;}
  20% {background:orange;}
  40% {background:yellowgreen;}
  60% {background:cyan;}
  80% {background:blue;}
  100% {background:violet;}
}

/* =========================
   📦 MINI PANEL (ARRIBA DERECHA)
========================= */
#miniPanel {
  position: fixed;
  top: 10px;
  right: 10px;
  width: 130px;
  background: rgba(0,0,0,0.6);
  border-radius: 10px;
  border: 1px solid rgba(255,255,255,0.2);
  color: yellow;
  font-size: 10px;
  text-align: center;
  padding: 5px;
}

#miniPanel button {
  width: 90%;
  margin: 3px 0;
  padding: 4px;
  font-size: 9px;
  border-radius: 6px;
  border: none;
  color: yellow;
  animation: rainbow 4s infinite;
}

/* =========================
   🧍 STICKMAN DERECHA
========================= */
#rightSide {
  position: absolute;
  right: 40px;
  top: 120px;
  display: flex;
  align-items: center;
  gap: 15px;
}

#stickman {
  width: 80px;
  height: 180px;
  position: relative;
}

.head {
  width: 28px;
  height: 28px;
  border: 3px solid white;
  border-radius: 50%;
  position: absolute;
  top: 0;
  left: 26px;
}

.body {
  width: 3px;
  height: 70px;
  background: white;
  position: absolute;
  top: 35px;
  left: 38px;
}

.armL, .armR {
  width: 40px;
  height: 3px;
  background: white;
  position: absolute;
  top: 55px;
}

.armL { left: 5px; transform: rotate(-25deg); }
.armR { right: 5px; transform: rotate(25deg); }

.legL, .legR {
  width: 40px;
  height: 3px;
  background: white;
  position: absolute;
  top: 105px;
}

.legL { left: 10px; transform: rotate(25deg); }
.legR { right: 10px; transform: rotate(-25deg); }
</style>
</head>

<body>

<!-- 📌 PANEL PRINCIPAL -->
<div id="panel">
  <div id="header">👹xit iOS 14💀</div>

  <button onclick="openFF()">Open Free Fire</button>
  <button onclick="brightness()">Brillo Máximo</button>
  <button onclick="gaming()">Modo Gaming</button>
  <button onclick="safeMode()">Modo Seguro</button>
</div>

<!-- 📦 MINI PANEL -->
<div id="miniPanel">
  MINI PANEL

  <button onclick="say('Head')">Head</button>
  <button onclick="say('Neck')">Neck</button>
  <button onclick="say('Chest')">Chest</button>
</div>

<!-- 🧍 STICKMAN -->
<div id="rightSide">
  <div id="stickman">
    <div class="head"></div>
    <div class="body"></div>
    <div class="armL"></div>
    <div class="armR"></div>
    <div class="legL"></div>
    <div class="legR"></div>
  </div>
</div>

<script>
let panel = document.getElementById("panel");
let header = document.getElementById("header");

/* DRAG PANEL */
let dragging = false, ox, oy;

header.addEventListener("mousedown", (e) => {
  dragging = true;
  ox = e.clientX - panel.offsetLeft;
  oy = e.clientY - panel.offsetTop;
});

document.addEventListener("mousemove", (e) => {
  if (dragging) {
    panel.style.left = (e.clientX - ox) + "px";
    panel.style.top = (e.clientY - oy) + "px";
  }
});

document.addEventListener("mouseup", () => {
  dragging = false;
});

/* VOZ */
function say(text) {
  let msg = new SpeechSynthesisUtterance(text + " seleccionado");
  speechSynthesis.speak(msg);
}

/* FUNCIONES ORIGINALES */
function openFF() {
  window.open("https://ff.garena.com", "_blank");
  setTimeout(() => {
    window.location.href =
      "intent://com.dts.freefireth#Intent;package=com.dts.freefireth;end";
  }, 1500);
}

function brightness() {
  document.body.style.filter = "brightness(200%)";
}

function gaming() {
  document.body.style.filter = "contrast(130%) saturate(150%)";
}

function safeMode() {
  document.body.style.filter = "none";
}
</script>

</body>
</html>
