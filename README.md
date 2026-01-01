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
  overflow: hidden;
}

/* LAYAR PEMBUKA */
#overlay {
  position: fixed;
  inset: 0;
  background: linear-gradient(135deg, #f9f6f2, #ffe6f0);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
  cursor: pointer;
}

#overlay h1 {
  color: #c94f7c;
  font-size: 24px;
  animation: pulse 1.5s infinite;
}

@keyframes pulse {
  0% { opacity: 0.5; }
  50% { opacity: 1; }
  100% { opacity: 0.5; }
}

/* KARTU */
.container {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.card {
  background: white;
  padding: 30px;
  max-width: 500px;
  border-radius: 20px;
  box-shadow: 0 4px 20px rgba(0,0,0,0.15);
  animation: fadeIn 2s ease;
  position: relative;
  z-index: 1;
}

h2 {
  color: #c94f7c;
}

p {
  font-size: 18px;
  line-height: 1.6;
  color: #333;
}

/* HATI */
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

@keyframes fadeIn {
  from { opacity: 0; transform: scale(0.9); }
  to { opacity: 1; transform: scale(1); }
}
</style>
</head>

<body>

<!-- OVERLAY -->
<div id="overlay">
  <h1>💗 Klik untuk membuka 💗</h1>
</div>

<div class="container">
  <div class="card">
    <h2>Untukmu</h2>
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
    <p>— Djati</p>
  </div>
</div>

<audio id="music" loop>
  <source src="MP3" type="audio/mpeg">
</audio>

<script>
const overlay = document.getElementById("overlay");
const music = document.getElementById("music");

overlay.addEventListener("click", async () => {
  try {
    await music.play();   // AUDIO UNLOCK
    overlay.style.display = "none";
    startHearts();
  } catch (e) {
    alert("Klik sekali lagi ya 💕");
  }
});

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

