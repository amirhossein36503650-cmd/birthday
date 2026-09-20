<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>تولدت مبارک ❤️</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      font-family: Tahoma, sans-serif;
      overflow: hidden;
      background: linear-gradient(135deg, #ff758c, #ff7eb3, #a18cd1);
      color: white;
    }

    /* صفحه رمز */
    #login {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 20px;
    }

    .login-box {
      width: 100%;
      max-width: 380px;
      padding: 35px 25px;
      text-align: center;
      border-radius: 25px;
      background: rgba(255,255,255,0.18);
      backdrop-filter: blur(15px);
      box-shadow: 0 15px 40px rgba(0,0,0,0.2);
      animation: appear 1s ease;
    }

    .lock {
      font-size: 60px;
      animation: heartbeat 1.5s infinite;
    }

    h1 {
      margin: 15px 0;
    }

    .login-box p {
      opacity: .9;
    }

    input {
      width: 100%;
      padding: 15px;
      border: none;
      outline: none;
      border-radius: 15px;
      text-align: center;
      font-size: 18px;
      margin: 15px 0;
    }

    button {
      width: 100%;
      padding: 15px;
      border: none;
      border-radius: 15px;
      background: white;
      color: #ff4f81;
      font-size: 18px;
      font-weight: bold;
      cursor: pointer;
      transition: .3s;
    }

    button:hover {
      transform: scale(1.04);
    }

    #error {
      color: #ffe1e1;
      display: none;
      margin-top: 12px;
    }

    /* صفحه تولد */
    #birthday {
      display: none;
      min-height: 100vh;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 20px;
      position: relative;
    }

    .card {
      position: relative;
      z-index: 5;
      max-width: 650px;
      padding: 45px 30px;
      border-radius: 30px;
      background: rgba(255,255,255,0.17);
      backdrop-filter: blur(12px);
      box-shadow: 0 20px 60px rgba(0,0,0,.2);
      animation: zoomIn 1.2s ease;
    }

    .cake {
      font-size: 80px;
      animation: float 2s infinite ease-in-out;
    }

    .title {
      font-size: clamp(38px, 10vw, 75px);
      margin: 10px 0;
      animation: heartbeat 1.5s infinite;
      text-shadow: 0 5px 20px rgba(0,0,0,.2);
    }

    .message {
      font-size: 20px;
      line-height: 2;
      margin-top: 20px;
    }

    .heart {
      position: fixed;
      bottom: -50px;
      font-size: 25px;
      animation: rise linear forwards;
      pointer-events: none;
      z-index: 1;
    }

    @keyframes rise {
      from {
        transform: translateY(0) rotate(0deg);
        opacity: 1;
      }
      to {
        transform: translateY(-110vh) rotate(360deg);
        opacity: 0;
      }
    }

    @keyframes heartbeat {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.08); }
    }

    @keyframes float {
      0%,100% { transform: translateY(0); }
      50% { transform: translateY(-12px); }
    }

    @keyframes appear {
      from {
        opacity: 0;
        transform: translateY(30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes zoomIn {
      from {
        opacity: 0;
        transform: scale(.6);
      }
      to {
        opacity: 1;
        transform: scale(1);
      }
    }

    .confetti {
      position: fixed;
      width: 8px;
      height: 15px;
      top: -20px;
      animation: confettiFall linear forwards;
      z-index: 10;
    }

    @keyframes confettiFall {
      to {
        transform: translateY(110vh) rotate(720deg);
      }
    }
  </style>
</head>

<body>

  <!-- صفحه ورود -->
  <section id="login">
    <div class="login-box">

      <div class="lock">🔐</div>

      <h1>یه سورپرایز داری ❤️</h1>

      <p>برای باز کردنش رمز رو وارد کن</p>

      <input
        type="password"
        id="password"
        placeholder="رمز عبور"
        onkeydown="if(event.key==='Enter') checkPassword()"
      >

      <button onclick="checkPassword()">
        باز کردن سورپرایز 🎁
      </button>

      <div id="error">
        رمز اشتباهه 😅 دوباره امتحان کن
      </div>

    </div>
  </section>


  <!-- صفحه تولد -->
  <section id="birthday">

    <div class="card">

      <div class="cake">🎂</div>

      <div class="title">
        تولدت مبارک ❤️
      </div>

      <div class="message">
        امیدوارم امسال برات پر از اتفاقای قشنگ،
        خنده‌های واقعی و لحظه‌های به‌یادماندنی باشه ✨
        <br><br>
        همیشه شاد و موفق باشی 🌹
        <br>
        تولدت مبارک 🎉❤️
      </div>

    </div>

  </section>


  <script>

    /* رمز سایت */
    const correctPassword = "1234";


    function checkPassword() {

      const password =
        document.getElementById("password").value;

      const error =
        document.getElementById("error");

      if (password === correctPassword) {

        document.getElementById("login").style.display = "none";

        document.getElementById("birthday").style.display = "flex";

        startHearts();

        startConfetti();

      } else {

        error.style.display = "block";

        document.getElementById("password").value = "";

      }
    }


    /* قلب‌های متحرک */
    function startHearts() {

      setInterval(() => {

        const heart = document.createElement("div");

        heart.className = "heart";

        const hearts = ["❤️","💗","💖","💕","💘"];

        heart.innerHTML =
          hearts[Math.floor(Math.random() * hearts.length)];

        heart.style.left =
          Math.random() * 100 + "vw";

        heart.style.animationDuration =
          (4 + Math.random() * 5) + "s";

        heart.style.fontSize =
          (18 + Math.random() * 25) + "px";

        document.body.appendChild(heart);

        setTimeout(() => {
          heart.remove();
        }, 9000);

      }, 300);

    }


    /* کاغذ رنگی */
    function startConfetti() {

      for (let i = 0; i < 120; i++) {

        setTimeout(() => {

          const piece =
            document.createElement("div");

          piece.className = "confetti";

          piece.style.left =
            Math.random() * 100 + "vw";

          piece.style.animationDuration =
            (2 + Math.random() * 4) + "s";

          piece.style.transform =
            `rotate(${Math.random() * 360}deg)`;

          document.body.appendChild(piece);

          setTimeout(() => {
            piece.remove();
          }, 6000);

        }, i * 25);

      }

    }

  </script>

</body>
</html>
