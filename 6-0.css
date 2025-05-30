<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Không gian tình yêu 3D gần</title>
  <style>
    body {
      margin: 0;
      overflow: hidden;
      height: 100vh;
      background: linear-gradient(45deg, #ffc0cb, #ffb6c1, #ff69b4);
      font-family: 'Arial', sans-serif;
      touch-action: none;
    }

    .scene {
      width: 100vw;
      height: 100vh;
      perspective: 1000px;
      overflow: hidden;
    }

    .world {
      width: 100%;
      height: 100%;
      transform-style: preserve-3d;
      transform: rotateX(0deg) rotateY(0deg);
      transition: transform 0.1s ease-out;
      position: relative;
    }

    .item {
      position: absolute;
      color: #fff0f5;
      font-weight: bold;
      text-shadow: 0 0 10px #ff69b4;
      font-size: 18px;
      padding: 6px 10px;
      border-radius: 12px;
      background: rgba(255, 182, 193, 0.3);
      animation: floatDown linear infinite;
    }

    @keyframes floatDown {
      0% {
        transform: translateY(-200px) translateZ(var(--z));
        opacity: 1;
      }
      100% {
        transform: translateY(100vh) translateZ(var(--z));
        opacity: 0;
      }
    }
  </style>
</head>
<body>

<div class="scene">
  <div class="world" id="world"></div>
</div>

<script>
  const messages = ['❤️', '💓', 'Tớ yêu T... H..', 'rất vui khi gặp đc cậu T H', '3', '7', '2011'];
  const world = document.getElementById('world');

  const screenWidth = window.innerWidth;
  const screenHeight = window.innerHeight;

  for (let i = 0; i < 250; i++) { // tăng mật độ lên 250 phần tử
    const el = document.createElement('div');
    el.className = 'item';
    el.textContent = messages[Math.floor(Math.random() * messages.length)];

    const x = Math.random() * (screenWidth - 30);  // gần sát 2 bên
    const y = Math.random() * (screenHeight - 30);
    const z = (Math.random() - 0.5) * 600;  // gần hơn (giảm độ sâu)

    el.style.left = `${x}px`;
    el.style.top = `${y}px`;
    el.style.setProperty('--z', `${z}px`);
    el.style.fontSize = `${Math.random() * 8 + 16}px`;  // đồng đều và dễ nhìn
    el.style.animationDuration = `${Math.random() * 3 + 6}s`;
    el.style.animationDelay = `${Math.random() * 2}s`;

    world.appendChild(el);
  }

  // Cảm ứng xoay
  let lastX, lastY, rotateX = 0, rotateY = 0;
  let isDragging = false;

  document.addEventListener('touchstart', (e) => {
    isDragging = true;
    lastX = e.touches[0].clientX;
    lastY = e.touches[0].clientY;
  });

  document.addEventListener('touchmove', (e) => {
    if (!isDragging) return;
    const deltaX = e.touches[0].clientX - lastX;
    const deltaY = e.touches[0].clientY - lastY;
    rotateY += deltaX * 0.3;
    rotateX -= deltaY * 0.3;
    world.style.transform = `rotateX(${rotateX}deg) rotateY(${rotateY}deg)`;
    lastX = e.touches[0].clientX;
    lastY = e.touches[0].clientY;
  });

  document.addEventListener('touchend', () => {
    isDragging = false;
  });
</script>

</body>
</html>