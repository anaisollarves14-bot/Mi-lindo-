<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>💖 Carta Especial by myeya 💖</title>
  <style>
    body {
      font-family: "Poppins", sans-serif;
      background-color: #fff;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
      flex-direction: column;
      text-align: center;
      color: #333;
      transition: background-color 0.4s ease;
    }

    h2, h3, p {
      margin: 10px 0;
    }

    .screen {
      display: none;
      width: 90%;
      max-width: 420px;
    }

    .active {
      display: block;
    }

    input {
      padding: 10px;
      width: 80%;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 1em;
      outline: none;
      margin-top: 10px;
    }

    button {
      margin-top: 15px;
      padding: 10px 20px;
      font-size: 1em;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: 0.3s;
      background-color: #ff4f81;
      color: white;
    }

    button:hover {
      background-color: #ff2a66;
    }

    .btn-container {
      display: flex;
      justify-content: center;
      gap: 15px;
      flex-wrap: wrap;
      margin-top: 25px;
    }

    .card {
      background-color: white;
      border-radius: 15px;
      padding: 25px;
      box-shadow: 0 0 15px rgba(0,0,0,0.1);
      animation: fadeIn 0.8s ease;
      text-align: left; 
    }

    .main-img {
      width: 280px;
      height: auto;
      margin-bottom: 15px;
      object-fit: contain;
      background: none;
      border: none;
      box-shadow: none;
    }

    @keyframes fadeIn {
      from {opacity: 0; transform: scale(0.95);}
      to {opacity: 1; transform: scale(1);}
    }

    #errorMessage {
      color: red;
      font-size: 0.9em;
      margin-top: 8px;
    }

    /* ✨ Texto tipo carta */
    .card p {
      text-align: justify;
      line-height: 1.6;
      font-size: 1em;
      margin-top: 15px;
    }

  </style>
</head>
<body>

  <!-- Pantalla de contraseña -->
  <div class="screen active" id="passwordScreen">
    <body background="3.jpeg">
    </body>
    <h2>🔒 Ingresa la contraseña</h2>
    <input type="password" id="passwordInput" placeholder="Escribe la clave...">
    <br>
    <button onclick="checkPassword()">Entrar</button>
    <p id="errorMessage"></p>
  </div>

  <div class="screen" id="menuScreen">
    <h2>💌 Dedicado para ti, amorcito 💌</h2>
    <p>Elige lo que quieres abrir:</p>
    <div class="btn-container">
      <button onclick="window.open('https://youtu.be/KnjtN2OaAG4?si=Ck0fS9xgrWqkC_4d')">🫶🏻 Opción 1</button>
      <button onclick="showLetter()">🫶🏻 Opción 2</button>
    </div>
  </div>

  <div class="screen" id="letterScreen">
    <div class="card">
      <video width="350" height="300" controls="">
        <source src="amol.mp4" type="video/mp4">
      </video>
      </p>
      <button onclick="goBack()">🔙 Volver</button>
    </div>
  </div>

  <script>
    const correctPassword = "1005";

    function checkPassword() {
      const input = document.getElementById("passwordInput").value.trim();
      const error = document.getElementById("errorMessage");

      if (input === correctPassword) {
        document.getElementById("passwordScreen").classList.remove("active");
        document.getElementById("menuScreen").classList.add("active");
        error.textContent = "";
      } else {
        error.textContent = "Contraseña incorrecta 💔";
      }
    }

    function showLetter() {
      document.getElementById("menuScreen").classList.remove("active");
      document.getElementById("letterScreen").classList.add("active");
    }

    function goBack() {
      document.getElementById("letterScreen").classList.remove("active");
      document.getElementById("menuScreen").classList.add("active");
    }
  </script>

</body>
</html>
