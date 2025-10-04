# Boda-Pablo-y-Abril
Boda Pablo y Abril
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Invitación de Boda - Abril & Pablo</title>
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Playfair+Display:wght@400;700&display=swap" rel="stylesheet">
<style>
body{margin:0;font-family:'Playfair Display',serif;background:radial-gradient(circle at top,#e8f0ff,#b5c6e0,#8da0c9);color:#2b2b2b;text-align:center;overflow-x:hidden}.overlay{position:fixed;top:0;left:0;width:100%;height:100%;background:radial-gradient(circle at center,rgba(255,255,255,0.95),rgba(200,200,255,0.85));display:flex;flex-direction:column;justify-content:center;align-items:center;z-index:10;transition:opacity 1.5s ease}.overlay h1{font-family:'Great Vibes',cursive;font-size:3em;color:#395886}.ring{width:120px;height:120px;background-image:url('ring.png');background-size:contain;background-repeat:no-repeat;cursor:pointer;animation:glow 2s infinite alternate,rotate 6s linear infinite}@keyframes glow{from{filter:drop-shadow(0 0 5px #c0c0ff)}to{filter:drop-shadow(0 0 15px #80a0ff)}}@keyframes rotate{0%{transform:rotate(0deg)}100%{transform:rotate(360deg)}}.invitation{opacity:0;transform:scale(0.5);transition:all 1.8s ease;position:relative;z-index:5}.invitation.active{opacity:1;transform:scale(1)}h2{font-family:'Great Vibes',cursive;font-size:2.5em;color:#395886}.section{background:rgba(255,255,255,0.8);margin:40px auto;padding:20px;border-radius:20px;max-width:700px;box-shadow:0 0 20px rgba(180,200,255,0.5);position:relative;overflow:hidden;transform:scale(0.95);opacity:0;transition:all 1.5s ease}.section.visible{transform:scale(1);opacity:1}.mapa iframe{width:100%;height:300px;border-radius:15px;border:none}#countdown{font-size:1.5em;color:#395886;font-weight:bold}footer{margin-top:20px;padding:20px}.whatsapp{display:inline-block;margin:10px;background:#25D366;color:white;padding:10px 20px;border-radius:50px;text-decoration:none;font-weight:bold}.comments{background:rgba(255,255,255,0.9);border-radius:15px;padding:20px}.luces,.flores{position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;overflow:hidden;z-index:1}.luz,.flor{position:absolute;border-radius:50%;opacity:0.8}.luz{width:6px;height:6px;background:white;animation:flotar 6s infinite ease-in-out}.flor{width:12px;height:12px;background:rgba(255,255,255,0.7);box-shadow:0 0 10px rgba(255,255,255,0.6);animation:flotar 12s linear infinite}@keyframes flotar{0%{transform:translateY(0) scale(1);opacity:1}100%{transform:translateY(-120vh) scale(0.5);opacity:0}}
</style>
</head>
<body>

<div class="overlay" id="overlay">
  <h1>Con amor eterno,<br>Abril & Pablo</h1>
  <div class="ring" id="ring"></div>
</div>

<audio id="music" loop>
  <source src="eternamente-enamorados.mp3" type="audio/mpeg">
</audio>

<div class="invitation" id="invitation">
  <h2>Nos complace invitarte a nuestra boda</h2>

  <div class="section">
    <p><strong>Abril Pérez Aguilar</strong><br>Hija de Eva Aguilar Rendón y Pedro Pérez Hernández</p>
    <p><strong>Pablo Eliel Tinoco Hernández</strong><br>Hijo de Saray Hernández Santana y Pablo Tinoco Carranza (finado)</p>
  </div>

  <div class="section">
    <h3>Ceremonia Religiosa</h3>
    <p>2:00 p.m. - Jardín El Abuelo, Tlaquiltenango</p>
    <h3>Recepción</h3>
    <p>4:00 p.m. - Jardín El Abuelo, Tlaquiltenango</p>
    <p><em>"Y los dos serán una sola carne" - Mateo 19:6</em></p>
  </div>

  <div class="section mapa">
    <h3>Ubicación</h3>
    <iframe src="https://www.bing.com/maps?&ty=18&q=Jard%C3%ADn%20El%20Abuelo%20Tlaquiltenango"></iframe>
  </div>

  <div class="section">
    <h3>Faltan...</h3>
    <div id="countdown"></div>
  </div>

  <div class="section comments">
    <h3>Deja tus buenos deseos 💌</h3>
    <form>
      <textarea rows="4" placeholder="Escribe aquí tu mensaje..." style="width: 90%; border-radius:10px; border:1px solid #ccc;"></textarea><br>
      <button type="button" style="padding:10px 20px; border:none; border-radius:20px; background:#395886; color:white;">Enviar</button>
    </form>
  </div>

  <footer class="section">
    <a href="https://wa.me/5217774914500" class="whatsapp">WhatsApp Abril 💐</a>
    <a href="https://wa.me/5217341123645" class="whatsapp">WhatsApp Pablo 🤵</a>
  </footer>
</div>

<div class="luces" id="luces"></div>
<div class="flores" id="flores"></div>

<script>
const overlay=document.getElementById('overlay');
const ring=document.getElementById('ring');
const invitation=document.getElementById('invitation');
const music=document.getElementById('music');
const lucesContainer=document.getElementById('luces');
const floresContainer=document.getElementById('flores');

// Luces
for(let i=0;i<25;i++){
  const luz=document.createElement('div');
  luz.classList.add('luz');
  luz.style.left=Math.random()*100+'vw';
  luz.style.animationDuration=(4+Math.random()*4)+'s';
  luz.style.animationDelay=Math.random()*3+'s';
  lucesContainer.appendChild(luz);
}

// Flores
for(let i=0;i<15;i++){
  const flor=document.createElement('div');
  flor.classList.add('flor');
  flor.style.left=Math.random()*100+'vw';
  flor.style.animationDuration=(10+Math.random()*10)+'s';
  flor.style.animationDelay=Math.random()*5+'s';
  floresContainer.appendChild(flor);
}

// Abrir invitación
ring.addEventListener('click',()=>{
  overlay.style.opacity='0';
  setTimeout(()=>{
    overlay.style.display='none';
    invitation.classList.add('active');
    music.play();
    checkVisibility();
  },1500);
});

// Contador
const eventDate=new Date("December 28, 2025 14:00:00").getTime();
const countdown=document.getElementById('countdown');
setInterval(()=>{
  const now=new Date().getTime();
  const distance=eventDate-now;
  const days=Math.floor(distance/(1000*60*60*24));
  const hours=Math.floor((distance%(1000*60*60*24))/(1000*60*60));
  const minutes=Math.floor((distance%(1000*60*60))/(1000*60));
  countdown.innerHTML=`${days} días, ${hours} horas, ${minutes} minutos`;
},1000);

// Zoom secciones scroll
const sections=document.querySelectorAll('.section');
function checkVisibility(){
  const triggerBottom=window.innerHeight/5*4;
  sections.forEach(section=>{
    const sectionTop=section.getBoundingClientRect().top;
    if(sectionTop<triggerBottom){section.classList.add('visible');}
  });
}
window.addEventListener('scroll',checkVisibility);
</script>

</body>
</html>
[eternamente.mp3](https://github.com/user-attachments/files/22699403/eternamente.mp3)
![ring](https://github.com/user-attachments/assets/30a564b9-a53f-47d7-b1d8-86d8ee6dc314)
![photo3](https://github.com/user-attachments/assets/6289e4eb-dd3d-44f9-a922-de1869c88be4)
![photo2](https://github.com/user-attachments/assets/e391a4c1-52d4-4e99-aae6-e3fec0bb3172)
![photo1](https://github.com/user-attachments/assets/ae162910-2ac7-419d-895b-e17c82571ea4)
![momento3](https://github.com/user-attachments/assets/26e8beb3-b96d-4169-8965-0aa715190ef2)
![momento2](https://github.com/user-attachments/assets/3e84dbc4-d532-4e19-ac17-8be932f90cb4)
![momento1](https://github.com/user-attachments/assets/0c01d5c7-609a-4c1d-a2e5-af3e5ac72b26)
