# Encuestas-Jaffet
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Encuesta San Valentín</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #ffe6f0;
      margin: 0;
      padding: 0;
    }
    .hidden {
      display: none;
    }
    .container {
      margin-top: 50px;
    }
    button {
      padding: 10px 20px;
      margin: 10px;
      font-size: 18px;
      cursor: pointer;
      border: none;
      border-radius: 8px;
    }
    #yesBtn {
      background-color: #ff4da6;
      color: white;
      transition: all 0.3s ease;
    }
    #noBtn {
      background-color: #999;
      color: white;
    }
    #finalMessage {
      font-size: 24px;
      color: #d63384;
      margin-top: 30px;
    }
    img {
      max-width: 300px;
      margin: 20px auto;
      display: block;
    }
  </style>
</head>
<body>
  <!-- Pantalla inicial -->
  <div id="startScreen" class="container">
    <h1>¿Estás lista?</h1>
    <button id="readyBtn">Si lo estoy</button>
  </div>

  <!-- Encuesta (segunda pantalla) -->
  <div id="surveyScreen" class="container hidden">
    <h2>¿Quieres pasar el 14 de febrero conmigo?</h2>
    <img src="https://i.ibb.co/BH5VZsMg/imagen.png" alt="Pregunta">
    <button id="yesBtn">Sí</button>
    <button id="noBtn">No</button>
    <div id="finalMessage" class="hidden"></div>
  </div>

  <script>
    const readyBtn = document.getElementById("readyBtn");
    const startScreen = document.getElementById("startScreen");
    const surveyScreen = document.getElementById("surveyScreen");
    const yesBtn = document.getElementById("yesBtn");
    const noBtn = document.getElementById("noBtn");
    const finalMessage = document.getElementById("finalMessage");

    let yesSize = 18; // tamaño inicial de fuente del botón "Sí"

    // Al presionar "Si lo estoy", se pasa a la encuesta
    readyBtn.addEventListener("click", () => {
      startScreen.classList.add("hidden");
      surveyScreen.classList.remove("hidden");
    });

    // Al presionar "No", el botón "Sí" se agranda
    noBtn.addEventListener("click", () => {
      yesSize += 10;
      yesBtn.style.fontSize = yesSize + "px";
      yesBtn.style.padding = (10 + yesSize/4) + "px " + (20 + yesSize/4) + "px";

      if (yesSize >= 80) {
        noBtn.classList.add("hidden");
      }
    });

    // Al presionar "Sí", aparece el mensaje final
    yesBtn.addEventListener("click", () => {
      yesBtn.classList.add("hidden");
      noBtn.classList.add("hidden");
      finalMessage.textContent = "Te espero para ese día mi princesa";
      finalMessage.classList.remove("hidden");
    });
  </script>
</body>
</html>
