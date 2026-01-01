# untuk perempuan yang anonim itu.
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kado Untukmu</title>

<style>
body {
  margin: 0;
  font-family: 'Georgia', serif;
  background: linear-gradient(135deg, #f9f6f2, #ffe6f0);
  text-align: center;
  padding: 50px;
  overflow: hidden;
}

.card {
  background: white;
  padding: 30px;
  border-radius: 20px;
  box-shadow: 0 4px 20px rgba(0,0,0,0.15);
  display: inline-block;
  max-width: 500px;
  animation: fadeIn 2s ease-in-out;
  position: relative;
  z-index: 1;
}

h1 {
  color: #c94f7c;
}

p {
  font-size: 18px;
  line-height: 1.6;
  color: #333;
}

/* Petunjuk musik */
#hint {
  margin-top: 15px;
  font-size: 14px;
  color: #999;
  animation: pulse 1.5s infinite;
}

@keyframes pulse {
  0% { opacity: .4 }
  50% { opacity: 1 }
  100% { opacity: .4 }
}

@keyframes fadeIn {
  from { opacity: 0; transform: scale(0.9); }
  to { opacity: 1; transform: scale(1); }
}

/* Hati */
.heart {
  position: fixed;
  top: -10px;
  font-size: 20px;
  color: #e63963;
  animation: fall linear infinite;
}

@keyframes fall {
  to {
    transform: translateY(100vh) rotate(360deg);
    opacity: 0;
  }
}
</style>
</head>

<body>

<div class="card">
  <h1>Untukmu </h1>
  <p>
Aku pernah patah,
bukan karena cinta itu salah,
tapi karena aku terlalu percaya
pada hal yang belum tentu tinggal.
      
Sejak itu aku belajar menahan,
bukan menutup.
Belajar menjaga hati,
bukan memenjarakannya.

Jika suatu hari
kamu datang tanpa memaksa,
hadir tanpa janji berlebihan,
dan membuatku bahagia dengan cara sederhana,
mungkin aku akan berani lagi,
bukan untuk jatuh,
tapi untuk percaya.
  </p>
  <div id="hint">Tap di mana saja untuk memulai musik 🎵</div>
  <p>— Djati</p>
</div>

<audio id="music" loop>
  <source src="musik.mpeg" type="audio/mpeg">
</audio>

<script>
const music = document.getElementById("music");
let started = false;

document.body.addEventListener("click", () => {
  if (!started) {
    music.play();
    started = true;
    document.getElementById("hint").style.display = "none";
    startHearts();
  }
}, { once: true });

function startHearts() {
  setInterval(() => {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "❤";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.animationDuration = (Math.random() * 3 + 2) + "s";
    document.body.appendChild(heart);
    setTimeout(() => heart.remove(), 5000);
  }, 500);
}
</script>

</body>
</html>
