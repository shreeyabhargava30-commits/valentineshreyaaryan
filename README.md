<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Valentine 💖</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
* {
  box-sizing: border-box;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

body {
  margin: 0;
  height: 100vh;
  background: linear-gradient(135deg, #ff9a9e, #fad0c4);
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Floating Hearts */
.heart {
  position: absolute;
  font-size: 18px;
  animation: floatUp 8s linear infinite;
  opacity: 0.7;
}

@keyframes floatUp {
  0% {
    transform: translateY(100vh) scale(0.5);
    opacity: 0;
  }
  10% { opacity: 1; }
  100% {
    transform: translateY(-10vh) scale(1.2);
    opacity: 0;
  }
}

/* Stars */
.star {
  position: absolute;
  width: 2px;
  height: 2px;
  background: white;
  border-radius: 50%;
  animation: twinkle 3s infinite ease-in-out;
}

@keyframes twinkle {
  0%, 100% { opacity: 0.2; }
  50% { opacity: 1; }
}

.card {
  background: white;
  padding: 30px 40px;
  border-radius: 20px;
  text-align: center;
  width: 320px;
  z-index: 2;
  box-shadow: 0 15px 35px rgba(0,0,0,0.25);
  animation: popIn 0.6s ease-out;
}

@keyframes popIn {
  from {
    transform: scale(0.8);
    opacity: 0;
  }
  to {
    transform: scale(1);
    opacity: 1;
  }
}

h1 {
  font-size: 22px;
  margin-bottom: 25px;
}

.buttons {
  position: relative;
  height: 60px;
}

button {
  padding: 10px 18px;
  border: none;
  border-radius: 25px;
  font-size: 16px;
  cursor: pointer;
}

#yesBtn {
  background-color: #ff4d6d;
  color: white;
}

#noBtn {
  background-color: #ddd;
  color: #333;
  position: absolute;
  left: 150px;
}
</style>
</head>

<body>

<div class="card">
  <h1>💘 Aryan, will you be my Valentine? 💘</h1>
  <div class="buttons" id="buttonArea">
    <button id="yesBtn" onclick="yesClick()">Yes ❤️</button>
    <button id="noBtn">No 😢</button>
  </div>
</div>

<script>
const noBtn = document.getElementById("noBtn");
const buttonArea = document.getElementById("buttonArea");

/* Move NO button only on hover/touch */
function moveNo() {
  const areaWidth = buttonArea.offsetWidth;
  const areaHeight = buttonArea.offsetHeight;
  const maxX = areaWidth - noBtn.offsetWidth;
  const maxY = areaHeight - noBtn.offsetHeight;

  noBtn.style.left = Math.random() * maxX + "px";
  noBtn.style.top = Math.random() * maxY + "px";
}

noBtn.addEventListener("mouseover", moveNo);
noBtn.addEventListener("touchstart", moveNo);

/* YES click */
function yesClick() {
  document.body.innerHTML = `
    <div style="
      height:100vh;
      background: linear-gradient(135deg,#ff9a9e,#fad0c4);
      display:flex;
      flex-direction:column;
      align-items:center;
      justify-content:center;
      color:white;
      text-align:center;
    ">
      <h1 style="font-size:30px;">💖 Yayyy Aryan! I knew it 😍💖</h1>
      <img src="https://media.giphy.com/media/l0MYt5jPR6QX5pnqM/giphy.gif"
           style="width:250px;border-radius:20px;">
    </div>
  `;
}

/* Hearts */
for (let i = 0; i < 20; i++) {
  const heart = document.createElement("div");
  heart.className = "heart";
  heart.innerHTML = "💖";
  heart.style.left = Math.random() * 100 + "vw";
  heart.style.animationDelay = Math.random() * 8 + "s";
  document.body.appendChild(heart);
}

/* Stars */
for (let i = 0; i < 40; i++) {
  const star = document.createElement("div");
  star.className = "star";
  star.style.left = Math.random() * 100 + "vw";
  star.style.top = Math.random() * 100 + "vh";
  star.style.animationDelay = Math.random() * 3 + "s";
  document.body.appendChild(star);
}
</script>

</body>
</html>

