[amorcito.html](https://github.com/user-attachments/files/22248800/amorcito.html)

<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Para ti, mi amor</title>
  <style>
    :root{
      --bg:#0f1724;
      --accent:#ff3b5c;
      --text:#e6eef8;
      --muted:#9fb0c9;
      --glass: rgba(255,255,255,0.06);
    }
    *{box-sizing:border-box;margin:0;padding:0}
    body{
      height:100%;
      background: radial-gradient(circle at 10% 10%, rgba(255,107,129,0.08), transparent 8%),
                  radial-gradient(circle at 90% 80%, rgba(255,255,255,0.03), transparent 15%),
                  var(--bg);
      color:var(--text);
      display:flex;
      align-items:center;
      justify-content:center;
      padding:24px;
      font-family:system-ui,Segoe UI,Roboto,Arial;
    }

    .card{
      max-width:760px;
      background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:18px;
      padding:28px;
      box-shadow:0 8px 30px rgba(2,6,23,0.6);
      border:1px solid rgba(255,255,255,0.04);
      display:grid;
      grid-template-columns:240px 1fr;
      gap:20px;
      align-items:center;
      backdrop-filter:blur(6px);
    }

    .heart-wrap{display:flex;align-items:center;justify-content:center}
    .heart{
      width:150px;
      height:150px;
      background:var(--accent);
      position:relative;
      transform:rotate(-45deg);
      animation:pulse 1.4s infinite;
      box-shadow:0 8px 20px rgba(255,59,92,0.4);
    }
    .heart:before,
    .heart:after{
      content:"";
      position:absolute;
      width:150px;
      height:150px;
      background:var(--accent);
      border-radius:50%;
    }
    .heart:before{top:-75px;left:0}
    .heart:after{left:75px;top:0}
    @keyframes pulse{
      0%{transform:rotate(-45deg) scale(0.95)}
      50%{transform:rotate(-45deg) scale(1.08)}
      100%{transform:rotate(-45deg) scale(0.95)}
    }

    .content{padding:6px 4px}
    h1{margin-bottom:8px;font-size:20px}
    .to{color:var(--muted);font-size:14px;margin-bottom:12px}

    .message{
      background:var(--glass);
      padding:14px;
      border-radius:12px;
      min-height:120px;
      display:flex;
      align-items:flex-start;
      overflow:hidden;
    }
    .typewriter{
      font-family:"Georgia",serif;
      line-height:1.5;
      font-size:16px;
      white-space:pre-wrap;
    }

    .controls{margin-top:12px;display:flex;gap:10px}
    .btn{
      background:linear-gradient(90deg,var(--accent),#ff6381);
      border:0;
      padding:10px 14px;
      border-radius:10px;
      color:#fff;
      font-weight:600;
      cursor:pointer;
      box-shadow:0 6px 18px rgba(255,59,92,0.2);
    }
    .btn.ghost{
      background:transparent;
      border:1px solid rgba(255,255,255,0.08);
      color:var(--muted);
    }
    footer{margin-top:14px;font-size:13px;color:var(--muted)}

    @media(max-width:680px){
      .card{grid-template-columns:1fr;text-align:center;padding:20px}
      .heart{margin:0 auto}
    }
    h1:hover{
        color: red;
        font-size: 25px;
        cursor: pointer;
    }
  </style>
</head>
<body>
  <main class="card">
    <div class="heart-wrap">
      <div class="heart"></div>
    </div>

    <div class="content">
      <div class="to">Para: <strong id="name">Kadie Paola Delgado Flores</strong></div>
      <h1>Un pequeño mensaje para ti</h1>

      <div class="message">
        <div class="typewriter" id="typewriter"></div>
      </div>

      <div class="controls">
        <button class="btn" id="reveal">❤️</button>
      </div>

      <footer>
       amorcito presiona ❤️
      </footer>
    </div>
  </main>

  <script>
    const defaultName = "Kadie Paola Delgado Flores";
    const defaultMessage = `Hola ${defaultName} ❤

Cada día a tu lado hace que el mundo sea más sencillo y bonitobonito🥰.
Tu risa es mi canción favorita y tus abrazos mi lugar seguroseguro🌹.

Gracias por ser tú. Te amo con todo mi corazón💓💍.`;

    const nameEl = document.getElementById("name");
    const typeEl = document.getElementById("typewriter");
    const revealBtn = document.getElementById("reveal");
    const personalBtn = document.getElementById("personalizar");

    nameEl.textContent = defaultName;

    function typeText(text, el, speed=28){
      el.textContent="";
      let i=0;
      const interval=setInterval(()=>{
        el.textContent+=text.charAt(i);
        i++;
        if(i>=text.length) clearInterval(interval);
      },speed);
    }

    revealBtn.addEventListener("click",()=>typeText(defaultMessage,typeEl));

    personalBtn.addEventListener("click",()=>{
      const newName=prompt("Escribe el nombre:",defaultName);
      if(newName===null) return;
      const newMsg=prompt("Escribe el mensaje:",defaultMessage);
      if(newName.trim()) nameEl.textContent=newName.trim();
      if(newMsg!==null && newMsg.trim()!==""){
        typeText(newMsg.replace(/\{name\}/g,newName.trim()),typeEl);
      }else{
        typeText(defaultMessage.replace(defaultName,newName.trim()),typeEl);
      }
    });
  </script>
</body>
</html>
