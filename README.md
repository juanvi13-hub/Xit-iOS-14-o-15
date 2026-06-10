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
  overflow: hidden;
  font-family: Arial;
}

/* PANEL */
#panel {
  width: 240px;
  position: fixed;
  top: 120px;
  left: 20px;
  background: rgba(0,0,0,0.65);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255,255,255,0.2);
  border-radius: 12px;
  color: white;
  box-shadow: 0 10px 30px rgba(0,0,0,0.5);
  z-index: 9999;
}

#header {
  padding: 10px;
  background: rgba(255,255,255,0.15);
  cursor: grab;
  font-weight: bold;
  text-align: center;
  border-top-left-radius: 12px;
  border-top-right-radius: 12px;
}

/* BOTONES */
button {
  width: 90%;
  margin: 8px 10px;
  padding: 8px;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  color: white;
  font-weight: bold;
  background: linear-gradient(270deg, red, orange, yellow, green, blue, purple);
  background-size: 1400% 1400%;
  animation: rainbow 5s ease infinite;
}

@keyframes rainbow {
  0% {background-position:0% 50%}
  50% {background-position:100% 50%}
  100% {background-position:0% 50%}
}

#msg {
  text-align: center;
  font-size: 12px;
  padding: 5px;
  color: #00ffcc;
}

/* STICKMAN */
.stickman {
  position: fixed;
  bottom: 20px;
  left: 60px;
  width: 60px;
  height: 120px;
}

.head {
  width: 20px;
  height: 20px;
  border: 3px solid white;
  border-radius: 50%;
  margin: 0 auto;
}

.body {
  width: 3px;
  height: 40px;
  background: white;
  margin: 0 auto;
}

.arm {
  width: 25px;
  height: 3px;
  background: white;
  position: absolute;
  top: 35px;
}

.arm.left { left: 0; transform: rotate(-30deg); }
.arm.right { right: 0; transform: rotate(30deg); }

.leg {
  width: 25px;
  height: 3px;
  background: white;
  position: absolute;
  top: 75px;
}

.leg.left { left: 5px; transform: rotate(40deg); }
.leg.right { right: 5px; transform: rotate(-40deg); }

/* 🔴 PUNTO ROJO */
.dot {
  position: fixed;
  width: 18px;
  height: 18px;
  background: red;
  border-radius: 50%;
  box-shadow: 0 0 15px red;
  display: none;
  z-index: 99999;
}

/* OPCIONES */
.stick-options {
  position: fixed;
  bottom: 30px;
  left: 140px;
  color: white;
  font-size: 12px;
  font-weight: bold;
}

.opt {
  margin: 6px 0;
  padding: 5px 8px;
  background: rgba(255,255,255,0.08);
  border: 1px solid rgba(255,255,255,0.2);
  border-radius: 6px;
  cursor: pointer;
}
</style>
</head>

<body>

<div id="panel">
  <div id="header">👹xit iOS 14💀</div>

  <button onclick="openFF()">Open Free Fire</button>
  <button onclick="brightness()">Brillo Máximo</button>
  <button onclick="gaming()">Modo Gaming</button>
  <button onclick="safeMode()">Modo Seguro</button>

  <div id="msg"></div>
</div>

<!-- STICKMAN -->
<div class="stickman">
  <div class="head"></div>
  <div class="body"></div>
  <div class="arm left"></div>
  <div class="arm right"></div>
  <div class="leg left"></div>
  <div class="leg right"></div>
</div>

<!-- OPCIONES -->
<div class="stick-options">
  <div class="opt" onclick="selectPart('head')">Cabeza activada</div>
  <div class="opt" onclick="selectPart('neck')">Cuello activado</div>
  <div class="opt" onclick="selectPart('chest')">Pecho activado</div>
</div>

<!-- PUNTO ROJO -->
<div id="dot" class="dot"></div>

<script>
let panel = document.getElementById("panel");
let header = document.getElementById("header");
let msg = document.getElementById("msg");
let dot = document.getElementById("dot");

let isDragging = false;
let offsetX, offsetY;

/* VOZ */
function speak(text){
  let speech = new SpeechSynthesisUtterance(text);
  speech.lang = "es-ES";
  speech.rate = 1;
  speechSynthesis.speak(speech);
}

/* DRAG */
header.addEventListener("mousedown", (e) => {
  isDragging = true;
  offsetX = e.clientX - panel.offsetLeft;
  offsetY = e.clientY - panel.offsetTop;
});

document.addEventListener("mousemove", (e) => {
  if (isDragging) {
    panel.style.left = (e.clientX - offsetX) + "px";
    panel.style.top = (e.clientY - offsetY) + "px";
  }
});

document.addEventListener("mouseup", () => {
  isDragging = false;
});

/* BOTONES PANEL */
function openFF(){ speak("opción activada"); }
function brightness(){ speak("opción activada"); document.body.style.filter="brightness(200%)"; }
function gaming(){ speak("opción activada"); document.body.style.filter="contrast(130%) saturate(150%)"; }
function safeMode(){ speak("opción activada"); document.body.style.filter="none"; }

/* OPCIONES STICKMAN */
function selectPart(part){

  speak(part + " activado");
  msg.innerHTML = part + " activado";

  dot.style.display = "block";

  if(part === "head"){
    dot.style.top = "85px";
    dot.style.left = "75px";
  }

  if(part === "neck"){
    dot.style.top = "110px";
    dot.style.left = "75px";
  }

  if(part === "chest"){
    dot.style.top = "135px";
    dot.style.left = "75px";
  }
}
</script>

</body>
</html>
