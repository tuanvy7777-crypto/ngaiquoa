<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>🎄 Merry Christmas 🎄</title>

<style>
/* ===== NỀN CHUNG ===== */
body {
  margin: 0;
  font-family: "Segoe UI", sans-serif;
  background: linear-gradient(#0f2027, #203a43, #2c5364);
  color: #fff;
  text-align: center;
  overflow-x: hidden;
}

/* ===== SECTION ===== */
section {
  min-height: 100vh;
  padding: 70px 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 22px;
  position: relative;
  z-index: 2;
}

.hidden { display: none; }

/* ===== TEXT ===== */
h1 {
  font-size: 42px;
  margin: 0;
}

h2 {
  font-size: 30px;
  margin: 0;
}

p {
  max-width: 600px;
  font-size: 18px;
  line-height: 1.7;
  opacity: 0.95;
}

/* ===== IMAGE ===== */
img {
  width: 260px;
  max-width: 80%;
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.4);
}

/* ===== BUTTON ===== */
button {
  padding: 12px 28px;
  font-size: 18px;
  border: none;
  border-radius: 30px;
  background: #ff4b5c;
  color: #fff;
  cursor: pointer;
  transition: 0.3s;
}

button:hover {
  background: #ff1e38;
  transform: scale(1.06);
}

/* ===== HEART ===== */
.heart {
  font-size: 80px;
  animation: beat 1s infinite;
}

@keyframes beat {
  0% { transform: scale(1); }
  50% { transform: scale(1.2); }
  100% { transform: scale(1); }
}

/* ===== SNOW ===== */
.snow {
  position: fixed;
  top: -10px;
  color: white;
  user-select: none;
  z-index: 1;
  animation: fall linear;
}

@keyframes fall {
  to { transform: translateY(110vh); }
}
</style>
</head>

<body>

<!-- ===== TRANG 1: NOEL ===== -->
<section>
  <h1>🎄 Merry Christmas 🎄</h1>
  <img src="igm1.jpg" alt="Noel">
  <p>
    Nhân dịp Giáng Sinh này,<br>
    Anh có vài điều muốn dành riêng cho em.
  </p>
  <button onclick="next(0)">Xem tiếp ➜</button>
</section>

<!-- ===== TRANG 2: KỶ NIỆM ===== -->
<section class="hidden">
  <h2>Đôi lời anh muốn nói với Don Don</h2>
  <img src="igm2.jpg" alt="Kỷ niệm">
  <p>
    Từ lúc anh quen biết em.<br>
    Anh bắt đầu để ý nhiều hơn đến những điều nhỏ nhặt.<br>
    Anh đã nhận ra cảm xúc của mình … <br>
    Không còn là vô tình nữa.<br>
    Nhân dịp này...
  </p>
  <button onclick="next(1)">Awww ngại quó</button>
</section>

<!-- ===== TRANG 3: TỎ TÌNH ===== -->
<section class="hidden">
  <div class="heart">❤️</div>
  <img src="igm3.jpg" alt="Tỏ tình">
  <h2>Anh có thể là người yêu em không?</h2>
  <button onclick="yes()">Em đồng ý 💕</button>
  <button onclick="no()">Em cần thời gian 💭</button>
</section>

<script>
/* ===== CHUYỂN TRANG ===== */
function next(i) {
  document.querySelectorAll("section")[i].classList.add("hidden");
  document.querySelectorAll("section")[i+1].classList.remove("hidden");
}

/* ===== PHẢN HỒI ===== */
function yes() {
  document.body.innerHTML = `
    <section>
      <h1>Anh hạnh phúc lắm </h1>
      <p>Cảm ơn em vì Giáng Sinh tuyệt vời nhất </p>
      <div class="heart">💖</div>
    </section>
  `;
}

function no() {
  alert("Anh vẫn trân trọng quyết định của em 💙");
}

/* ===== TUYẾT RƠI ===== */
function snow() {
  const s = document.createElement("div");
  s.className = "snow";
  s.innerText = "❄";
  s.style.left = Math.random() * window.innerWidth + "px";
  s.style.fontSize = (Math.random() * 10 + 10) + "px";
  s.style.animationDuration = (Math.random() * 5 + 5) + "s";
  document.body.appendChild(s);
  setTimeout(() => s.remove(), 10000);
}
setInterval(snow, 200);
</script>

</body>
</html>
