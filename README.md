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

/* HEADER */
#header {
  padding: 10px;
  background: rgba(255,255,255,0.15);
  cursor: grab;
  font-weight: bold;
  text-align: center;
  border-top-left-radius: 12px;
  border-top-right-radius: 12px;
}

/* BOTONES RAINBOW */
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

button:hover {
  transform: scale(1.03);
}

@keyframes rainbow {
  0% {background-position:0% 50%}
  50% {background-position:100% 50%}
  100% {background-position:0% 50%}
}

/* mensaje */
#msg {
  text-align: center;
  font-size: 12px;
  padding: 5px;
  color: #00ffcc;
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

<script>
let panel = document.getElementById("panel");
let header = document.getElementById("header");
let msg = document.getElementById("msg");

let isDragging = false;
let offsetX, offsetY;

/* VOZ */
function speak(text){
  let msg = new SpeechSynthesisUtterance(text);
  msg.lang = "es-ES";
  msg.rate = 1;
  speechSynthesis.speak(msg);
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

/* contador */
let activadas = 0;

function checkDone(name) {
  activadas++;

  speak(name + " activada");
  msg.innerHTML = "✅ " + name + " activada";

  if (activadas >= 4) {
    speak("opción activada");
  }
}

/* BOTONES */
function openFF() {
  speak("abriendo free fire");

  window.open("https://ff.garena.com", "_blank");

  setTimeout(() => {
    window.location.href =
      "intent://com.dts.freefireth#Intent;package=com.dts.freefireth;end";
  }, 1500);

  checkDone("Open Free Fire");
}

function brightness() {
  document.body.style.filter = "brightness(200%)";
  checkDone("Brillo máximo");
}

function gaming() {
  document.body.style.filter = "contrast(130%) saturate(150%)";
  checkDone("Modo gaming");
}

function safeMode() {
  document.body.style.filter = "none";
  checkDone("Modo seguro");
}
</script>

</body>
</html>
