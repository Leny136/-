<html lang="es">
<head>
<meta charset="UTF-8">
<title></title> <!-- Pestaña vacía -->
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body{
  font-family: Arial, sans-serif;
  background: linear-gradient(180deg,#ffd1dc,#ffe6f0);
  padding: 20px;
  min-height: 100vh;
}

.card{
  background:#fff;
  width: 90%;
  max-width: 500px;
  border-radius: 25px;
  padding: 20px;
  text-align: center;
  box-shadow: 0 10px 25px rgba(0,0,0,.15);
  margin: 20px auto;
}

h1{
  color:#ff4d6d;
  font-size: 22px;
  margin-bottom: 15px;
}

.hidden{
  display: none !important;
}

button{
  width: 100%;
  padding: 15px;
  margin: 10px 0;
  border: none;
  border-radius: 30px;
  font-size: 18px;
  cursor: pointer;
  transition: all 0.2s ease;
}

.yes{
  background:#ff4d6d;
  color: white;
}

.no{
  background:#f2f2f2;
  color: #333;
}

.option{
  background:#ffe6ee;
  border: 2px solid transparent;
  color: #333;
  margin: 0;
  font-size: 14px;
}

.option.selected{
  border-color:#ff4d6d;
  background:#ffd1dc;
  color: #333;
}

.confirm-btn{
  background:#ff4d6d;
  color: white;
  margin-top: 20px;
}

img{
  width: 100%;
  border-radius: 20px;
  margin: 10px 0;
}

/* -------------------- AJUSTES PARA QUE TODAS LAS IMÁGENES QUEDEN IGUALES -------------------- */
.img-container {
  width: 100%;
  height: 120px; /* Alto fijo para todas */
  border-radius: 10px;
  overflow: hidden; /* Oculta las partes que sobresalgan */
  background-color: #f0f0f0; /* Fondo gris claro si la imagen no ocupa todo */
}

.option-img {
  width: 100%;
  height: 100%;
  object-fit: cover; /* Ajusta la imagen sin deformarla */
  object-position: center; /* Centra la imagen en el contenedor */
  margin: 0;
  border-radius: 0; /* Quita el borde redondeado para que no choque con el contenedor */
}

/* Estilos para los elementos flotantes */
.floating-love {
  position: fixed;
  bottom: -20px;
  font-size: 40px;
  color: #ff4d6d;
  pointer-events: none;
  z-index: 100;
  animation: floatUp 15s linear forwards;
}

@keyframes floatUp {
  to {
    transform: translateY(-90vh);
    opacity: 0;
  }
}

/* -------------------- DISEÑO DE TARJETAS COMIDA Y ACTIVIDADES -------------------- */
.options-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 15px;
  margin-bottom: 20px;
}

.option-card {
  background: #fff;
  border: 3px solid #e0e0e0;
  border-radius: 15px;
  padding: 10px;
  text-align: center;
  position: relative;
  transition: all 0.2s ease;
}

.option-card.selected {
  border: 3px solid #ff4d6d;
}

.check-mark {
  position: absolute;
  top: -12px;
  right: -12px;
  background: #ff4d6d;
  color: #fff;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
}

.option-card .option {
  width: 100%;
  padding: 10px;
}

/* Estilo iframe para Google Form */
#googleFormIframe {
  width: 100%;
  height: 600px;
  border: none;
  margin-top: 20px;
  border-radius: 15px;
}
</style>
</head>
<body>

<!-- -------------------- PASOS -------------------- -->

<div class="card" id="step1">
  <h1>¿Me dejarías ser tu San Valentín?</h1>
  <img src="https://i.postimg.cc/y6PfpPqK/906a0aa0178e34058edb3d30fb183608.jpg" alt="Foto bonita">
  <button class="yes" id="yesBtn">Sí</button>
  <button class="no" id="noBtn">No</button>
</div>

<div class="card hidden" id="step2">
  <h1>¿Eres libre este día?</h1>
  <button class="option date-option">14/02/2026 – 19:00</button>
  <button class="confirm-btn" id="confirmDate">Confirmar fecha</button>
</div>

<div class="card hidden" id="step3">
  <h1>¿Qué te gustaría comer?</h1>
  <div class="options-grid">
    <!-- TODAS LAS COMIDAS CON SUS IMÁGENES -->
    <div class="option-card" data-type="food">
      <div class="check-mark hidden">✔</div>
      <div class="img-container">
        <img src="https://i.postimg.cc/0j52dq3C/49a568be608131ec346df78d6bc47669.jpg" class="option-img" alt="Comida normalita">
      </div>
      <button class="option food-option">Comida normalita</button>
    </div>
    <div class="option-card" data-type="food">
      <div class="check-mark hidden">✔</div>
      <div class="img-container">
        <img src="https://i.postimg.cc/Vv7sKVPn/9bebf66161281e8aaffd0fed28227d4a.jpg" class="option-img" alt="Hamburguesa">
      </div>
      <button class="option food-option">Hamburguesa grasosa</button>
    </div>
    <div class="option-card" data-type="food">
      <div class="check-mark hidden">✔</div>
      <div class="img-container">
        <img src="https://i.postimg.cc/rFmwDM5g/1e92708d4c30a0c225cd6e2a8d6aac8b.jpg" class="option-img" alt="Torta">
      </div>
      <button class="option food-option">Rica torta de frutilla 🫦</button>
    </div>
    <div class="option-card" data-type="food">
      <div class="check-mark hidden">✔</div>
      <div class="img-container">
        <img src="https://i.postimg.cc/KYnZ6zyc/2dfde0f8ea2865d04cfc47c94c43345a.jpg" class="option-img" alt="Diabetes">
      </div>
      <button class="option food-option">Tengamos diabetes juntos 😚</button>
    </div>
    <div class="option-card" data-type="food">
      <div class="check-mark hidden">✔</div>
      <div class="img-container">
        <img src="https://i.postimg.cc/9FrcW1jD/e3d01be8b77d951b0ba79ea8e3cdc84e.jpg" class="option-img" alt="Salchicha">
      </div>
      <button class="option food-option">Rica salchicha, como tu pene jejeje</button>
    </div>
    <div class="option-card" data-type="food">
      <div class="check-mark hidden">✔</div>
      <div class="img-container">
        <img src="https://i.postimg.cc/fL8hsS2H/7a12a5be6bb3e84f17762f65a4d35fd7.jpg" class="option-img" alt="Sanguchitos">
      </div>
      <button class="option food-option">Una de las cosas más ricas, aparte de vos guapo 😘</button>
    </div>
  </div>
  <button class="confirm-btn" id="confirmFood">Confirmar comida</button>
</div>

<div class="card hidden" id="step4">
  <h1>¿Qué te gustaría hacer?</h1>
  <div class="options-grid">
    <!-- TODAS LAS ACTIVIDADES CON SUS IMÁGENES -->
    <div class="option-card" data-type="activity">
      <div class="check-mark hidden">✔</div>
      <div class="img-container">
        <img src="https://i.postimg.cc/sf0R0SZr/d95337835c0b2020ae13ebaf333ad1bf.jpg" class="option-img" alt="Dormir con tu amor">
      </div>
      <button class="option activity-option">Dormir todo el día con el amor de tu vida 🥴</button>
    </div>
    <div class="option-card" data-type="activity">
      <div class="check-mark hidden">✔</div>
      <div class="img-container">
        <img src="https://i.postimg.cc/kXKq6GB9/4a290a01c184f6f48711be73d66713e7.jpg" class="option-img" alt="Ir de compras">
      </div>
      <button class="option activity-option">Ir de compras con tu familia hermosa 🥰</button>
    </div>
    <div class="option-card" data-type="activity">
      <div class="check-mark hidden">✔</div>
      <div class="img-container">
        <img src="https://i.postimg.cc/k5c4pc8C/6ddc2a2ed9d22bb2070c4c69bfb2c38c.jpg" class="option-img" alt="Picnic">
      </div>
      <button class="option activity-option">Picnic barato, porque somos humildes 😌</button>
    </div>
    <div class="option-card" data-type="activity">
      <div class="check-mark hidden">✔</div>
      <div class="img-container">
        <img src="https://i.postimg.cc/507DTdjx/61eb149d8ca7eb84bf0b552a9b450117.jpg" class="option-img" alt="Hornear">
      </div>
      <button class="option activity-option">Hornear conmigo, el hombre más hermoso 🫦</button>
    </div>
    <div class="option-card" data-type="activity">
      <div class="check-mark hidden">✔</div>
      <div class="img-container">
        <img src="https://i.postimg.cc/bY5KRhKT/600f994d036971dbe4e4b65e0325d3ae.jpg" class="option-img" alt="Sesión de fotos">
      </div>
      <button class="option activity-option">Una sesión de fotos juntos o solos 😼</button>
    </div>
    <div class="option-card" data-type="activity">
      <div class="check-mark hidden">✔</div>
      <div class="img-container">
        <img src="https://i.postimg.cc/C1LWcLhJ/c31849532bc9d07231f465f546aa1972.jpg" class="option-img" alt="Hacer ejercicio">
      </div>
      <button class="option activity-option">Hacer ejercicio para que veas mí gran culo y te enamores más 😏</button>
    </div>
  </div>
  <button class="confirm-btn" id="confirmActivity">Confirmar opción</button>
</div>

<div class="card hidden" id="final">
  <img src="https://i.postimg.cc/G9wd28YK/8a5cf78cf7cf0c8f23e081ec6dea3ccc.jpg" alt="Feliz San Valentín">
  <h1>
    ¡Ya está todo listo para nuestra cita!<br><br>
    No te atrevas a faltar eh. Te estaré<br><br>
    esperando y si no vienes, mi corazón se<br><br>
    va a hacer añicos, ¡nos vemos guapo! 😘
  </h1>

  <!-- Iframe para Google Form -->
  <iframe id="googleFormIframe" src=""></iframe>
</div>

<script>
// Variables principales
const yesBtn = document.getElementById("yesBtn");
const noBtn = document.getElementById("noBtn");
let scale = 1;

// Lista de elementos lindos que aparecerán
const loveElements = [
  "💖", "💗", "💕", "💘", "❤️", 
  "Te amo", "Mi amor", "Eres mío", 
  "😍", "✨", "Te quiero", "Amor mio",
  "Mi príncipe", "Hermoso mío", "Pecas", "Me perteneces",
  "Eres mi mundo", "Mi calabacín", "Encantador", "Te estoy vigilando",
  "Siempre te estoy viendo", "Guapo", "Grandioso", "Brillante",
  "Bello", "😘", "🫦", "🥰",
  "💝", "💓", "💞", "❤️‍🩹",
  "💋", "❣️", "Cariño", "Dulzura",
  "Tesoro", "Corazón", "cielo", "Ternura",
  "Sol", "Luna",
];

// Función para crear elementos flotantes
function showLove() {
  const love = document.createElement("div");
  love.className = "floating-love";
  love.innerText = loveElements[Math.floor(Math.random() * loveElements.length)];
  love.style.left = Math.random() * 100 + "vw";
  love.style.animationDuration = (2 + Math.random() * 2) + "s";
  love.style.fontSize = (18 + Math.random() * 8) + "px";
  document.body.appendChild(love);
  setTimeout(() => love.remove(), 15000);
}

// Efecto botón "No"
noBtn.onclick = () => {
  scale += 0.2;
  yesBtn.style.transform = `scale(${scale})`;
};

// Botón "Sí"
yesBtn.onclick = () => goToStep(2);

// Selección de fecha
document.querySelectorAll(".date-option").forEach(btn => {
  btn.onclick = () => {
    document.querySelectorAll(".date-option").forEach(b => b.classList.remove("selected"));
    btn.classList.add("selected");
    showLove();
  }
});

// SELECCIÓN DE COMIDAS (activa borde y tilde)
document.querySelectorAll(".food-option").forEach(btn => {
  btn.onclick = () => {
    const card = btn.closest(".option-card");
    card.classList.toggle("selected");
    const check = card.querySelector(".check-mark");
    check.classList.toggle("hidden");
    showLove();
  }
});

// SELECCIÓN DE ACTIVIDADES (activa borde y tilde)
document.querySelectorAll(".activity-option").forEach(btn => {
  btn.onclick = () => {
    const card = btn.closest(".option-card");
    card.classList.toggle("selected");
    const check = card.querySelector(".check-mark");
    check.classList.toggle("hidden");
    showLove();
  }
});

// ID de tu Google Form (solo reemplazá este link con tu formulario real)
const googleFormURL = "https://docs.google.com/forms/d/e/1FAIpQLSc50_B4v9aFjuZZLLe7Dnt2fjz28-sFiDH6dtK8m3CAV8CXmA/viewform?embedded=true";

// Botón confirmar fecha
document.getElementById("confirmDate").onclick = () => {
  if(document.querySelector(".date-option.selected")) {
    goToStep(3);
    // Abrir formulario en iframe
    document.getElementById("googleFormIframe").src = googleFormURL;
  } else {
    alert("Elige una fecha primero amor ❤️");
  }
};

// Botón confirmar comida
document.getElementById("confirmFood").onclick = () => {
  if(document.querySelector(".option-card.selected[data-type='food']")) {
    goToStep(4);
    document.getElementById("googleFormIframe").src = googleFormURL;
  } else {
    alert("Elige al menos una comida ❤️");
  }
};

// Botón confirmar actividades
document.getElementById("confirmActivity").onclick = () => {
  if(document.querySelector(".option-card.selected[data-type='activity']")) {
    goToStep(5);
    document.getElementById("googleFormIframe").src = googleFormURL;
  } else {
    alert("Elige al menos una actividad ❤️");
  }
};

// Función para cambiar de paso
function goToStep(stepNumber) {
  document.querySelectorAll(".card").forEach(card => card.classList.add("hidden"));
  if(stepNumber === 5) document.getElementById("final").classList.remove("hidden");
  else document.getElementById("step" + stepNumber).classList.remove("hidden");
}
</script>
</body>
</html>
