<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Tỏ Tình Trong Bầu Trời Sao</title>
  <style>
    body {
      margin: 0;
      overflow: hidden;
      background: black;
      font-family: 'Segoe UI', sans-serif;
      perspective: 1000px;
    }

    .star {
      position: absolute;
      background: white;
      border-radius: 50%;
      opacity: 0.8;
      animation: twinkle 2s infinite alternate;
    }

    @keyframes twinkle {
      from { opacity: 0.3; }
      to { opacity: 0.9; }
    }

    .message {
      position: absolute;
      color: white;
      font-size: 24px;
      white-space: nowrap;
      text-shadow: 0 0 5px #ff69b4, 0 0 10px #ff1493;
      animation: fall 10s linear forwards;
      transform-origin: center;
    }

    @keyframes fall {
      0% {
        top: -50px;
        opacity: 0;
        transform: rotateX(0deg) scale(1);
      }
      10% {
        opacity: 1;
      }
      100% {
        top: 100vh;
        opacity: 0;
        transform: rotateX(360deg) scale(0.5);
      }
    }

    .heart {
      position: absolute;
      width: 10px;
      height: 10px;
      background: red;
      transform: rotate(45deg);
      animation: heartFall 6s linear forwards;
    }

    .heart::before,
    .heart::after {
      content: "";
      position: absolute;
      width: 10px;
      height: 10px;
      background: red;
      border-radius: 50%;
    }

    .heart::before {
      top: -5px;
      left: 0;
    }

    .heart::after {
      left: -5px;
      top: 0;
    }

    @keyframes heartFall {
      0% {
        top: -10px;
        opacity: 1;
      }
      100% {
        top: 100vh;
        opacity: 0;
      }
    }
  </style>
</head>
<body>

<script>
  // Tạo các chấm sao li ti
  for (let i = 0; i < 150; i++) {
    const star = document.createElement("div");
    star.className = "star";
    const size = Math.random() * 2 + 1;
    star.style.width = size + "px";
    star.style.height = size + "px";
    star.style.left = Math.random() * window.innerWidth + "px";
    star.style.top = Math.random() * window.innerHeight + "px";
    star.style.animationDuration = (Math.random() * 2 + 1) + "s";
    document.body.appendChild(star);
  }

  // Danh sách câu tỏ tình
  const messages = [
    "Em thích anh.",
    "Em muốn lúc nào cũng được nhìn thấy anh.",
    "Anh là người em luôn nghĩ đến mỗi sáng thức dậy.",
    "Em không cần gì nhiều, chỉ cần có anh bên cạnh.",
    "Anh là giấc mơ đẹp nhất trong lòng em.",
    "Mỗi ngày trôi qua cùng anh là một ngày tuyệt vời.",
    "Trái tim em đã lỡ dành trọn cho anh mất rồi.",
    "Em chỉ muốn thấy anh cười mỗi ngày thôi.",
    "Gặp được anh là điều tuyệt vời nhất trong cuộc đời em.",
    "Em yêu anh ít hơn anh yêu em 😆.",
    "Em không cần ai khác, chỉ cần anh.",
    "Dù mai này ra sao, tình cảm em dành cho anh vẫn vẹn nguyên.",
    "Ở bên anh, em thấy mọi muộn phiền đều tan biến.",
    "Anh là ánh sáng ấm áp nhất trong lòng em.",
    "Em yêu anh – nhẹ nhàng nhưng là mãi mãi."
  ];

  // Tạo chữ rơi
  function createMessage() {
    const msg = document.createElement("div");
    msg.className = "message";
    msg.innerText = messages[Math.floor(Math.random() * messages.length)];
    msg.style.left = Math.random() * window.innerWidth + "px";
    msg.style.fontSize = (20 + Math.random() * 16) + "px";
    msg.style.animationDuration = (6 + Math.random() * 5) + "s";
    document.body.appendChild(msg);
    setTimeout(() => msg.remove(), 11000);
  }

  // Tạo trái tim bay
  function createHeart() {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.style.left = Math.random() * window.innerWidth + "px";
    heart.style.animationDuration = (3 + Math.random() * 3) + "s";
    document.body.appendChild(heart);
    setTimeout(() => heart.remove(), 6000);
  }

  // Tạo hiệu ứng liên tục
  setInterval(createMessage, 400);
  setInterval(createHeart, 200);
</script>

</body>
</html>
