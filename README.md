[practica2.html](https://github.com/user-attachments/files/22248454/practica2.html)
<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Para ti, mi amor</title>
  <style>
    :root{
      --bg:#0f1724;
      --card:#0b1220;
      --accent:#ff6b81;
      --glass: rgba(255,255,255,0.06);
      --text:#e6eef8;
      --muted:#9fb0c9;
    }
    * {box-sizing:border-box}
    html,body{height:100%;margin:0;font-family:system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial}
    body{
      background: radial-gradient(circle at 10% 10%, rgba(255,107,129,0.06), transparent 8%),
                  radial-gradient(circle at 90% 80%, rgba(255,255,255,0.02), transparent 15%),
                  var(--bg);
      color:var(--text);
      display:flex;
      align-items:center;
      justify-content:center;
      padding:24px;
    }

    .card{
      width:100%;
      max-width:760px;
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:18px;
      padding:28px;
      box-shadow: 0 8px 30px rgba(2,6,23,0.6);
      backdrop-filter: blur(6px);
      border: 1px solid rgba(255,255,255,0.04);
      display:grid;
      grid-template-columns: 240px 1fr;
      gap:20px;
      align-items:center;
    }

    .heart-wrap{
      display:flex;
      align-items:center;
      justify-content:center;
      padding:12px;
    }

    .heart{
      width:160px;
      height:160px;
      position:relative;
      transform:scale(1);
      animation: pulse 1.6s infinite;
      filter: drop-shadow(0 8px 24px rgba(255,107,129,0.18));
    }
    .heart:before, .heart:after{
      content:"";
      position:absolute;
      width:100px;
      height:160px;
      background:linear-gradient(180deg,var(--accent), #ff3a63);
      border-radius:100px 100px 0 0;
      top:0;
      left:30px;
      transform:rotate(-45deg);
    }
    .heart:after{
      left:0;
      transform:rotate(45deg);
    }
    @keyframes pulse{
      0%{ transform:scale(0.98) }
      50%{ transform:scale(1.06) }
      100%{ transform:scale(0.98) }
    }

    .content{
      padding:6px 4px;
    }

    h1{
      margin:0 0 8px 0;
      font-size:20px;
      letter-spacing:0.2px;
    }
    .to{
      color:var(--muted);
      font-size:14px;
      margin-bottom:12px;
    }

    .message{
      background:var(--glass);
      padding:14px;
      border-radius:12px;
      min-height:120px;
      display:flex;
      align-items:flex-start;
      position:relative;
      overflow:hidden;
    }

    .typewriter{
      font-family: "Georgia", serif;
      line-height:1.5;
      font-size:16px;
      color:var(--text);
      white-space:pre-wrap;
      word-break:break-word;
    }

    .controls{
      margin-top:12px;
      display:flex;
      gap:10px;
      align-items:center;
    }
    .btn{
      background:linear-gradient(90deg,var(--accent), #ff3a63);
      border:0;
      padding:10px 14px;
      border-radius:10px;
      color:white;
      cursor:pointer;
      font-weight:600;
      box-shadow: 0 6px 18px rgba(255,107,129,0.14);
    }
    .btn.ghost{
      background:transparent;
      border:1px solid rgba(255,255,255,0.06);
      color:var(--muted);
      font-weight:600;
    }

    footer{
      margin-top:14px;
      font-size:13px;
      color:var(--muted);
    }

    /* responsive */
    @media (max-width:680px){
      .card{ grid-template-columns: 1fr; text-align:center; gap:12px; padding:20px}
      .heart{ margin:0 auto }
      .content{ padding-top:0 }
    }
  </style>
</head>
<body>
  <main class="card" role="main">
    <div class="heart-wrap" aria-hidden="true">
      <div class="heart"></div>
    </div>

    <div class="content">
      <div class="to">Para: <strong id="name">Mi Amor</strong></div>
      <h1>Un pequeño mensaje para ti</h1>

      <div class="message" id="messageBox" aria-live="polite">
        <div class="typewriter" id="typewriter">
          <!-- El texto aparecerá aquí -->
        </div>
      </div>

      <div class="controls">
        <button class="btn" id="reveal">Revelar mensaje</button>
        
      </div>

     <footer>
        Te amo tanto mi corazon besitos changuita.
      </footer>
    </div>
  </main>

  <script>
    // Cambia aquí el nombre y el mensaje si quieres (usa comillas).
    const defaultName = "kadie Paola Delgado Flores ❤️🌹";
    const defaultMessage = `Hola ${defaultName} ❤

Cada día a tu lado hace que el mundo sea más sencillo y bonito.
Tu risa es mi canción favorita y tus abrazos mi lugar seguro.

Gracias por ser tú. Te quiero más de lo que las palabras alcanzan a decir.`;

    const nameEl = document.getElementById('name');
    const typeEl = document.getElementById('typewriter');
    const revealBtn = document.getElementById('reveal');
    const personalBtn = document.getElementById('personalizar');

    // Preload default
    nameEl.textContent = defaultName;

    function typeText(text, el, speed=28){
      el.textContent = "";
      let i = 0;
      const interval = setInterval(() => {
        el.textContent += text.charAt(i);
        i++;
        if(i >= text.length) clearInterval(interval);
      }, speed);
    }

    revealBtn.addEventListener('click', () => {
      typeText(defaultMessage, typeEl);
    });

    personalBtn.addEventListener('click', () => {
      const newName = prompt("Escribe el nombre que quieres mostrar :", defaultName);
      if(newName === null) return;
      const newMsg = prompt("Escribe el mensaje (puedes usar varias líneas). Puedes dejar vacío para usar el mensaje por defecto:", defaultMessage);
      if(newName.trim()) nameEl.textContent = newName.trim();
      if(newMsg !== null && newMsg.trim() !== "") {
        // Si el usuario escribió un mensaje nuevo, úsalo para escribir
        const final = newMsg.replace(/\{name\}/g, newName.trim() || defaultName);
        typeText(final, typeEl);
      } else {
        // usar mensaje por defecto con nombre actualizado
        const final = defaultMessage.replace(defaultName, newName.trim() || defaultName);
        typeText(final, typeEl);
      }
    });

    // opcional: mostrar automáticamente después de unos segundos
    // setTimeout(() => revealBtn.click(), 900);
  </script>
</body>
</html>
