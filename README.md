
<html lang="pl">
<head>
  <meta charset="utf-8" />
  <title> KlimakSzef • TWITCH Neon</title>
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700;900&display=swap" rel="stylesheet">
  <style>
    :root{
      --neon-color: #800080; /* kolor neonu */
      --width: 360px;
      --height: 180px;
      --speed: 6s; /* czas obrotu */
      --font: "Orbitron", sans-serif;
    }
    *{box-sizing:border-box}
    html,body{
      height:100%;
      margin:0;
      background:transparent; /* przezroczyste tło */
      font-family:var(--font);
    }
    .wrap{height:100%;display:flex;align-items:center;justify-content:center}
    .flip-box{width:var(--width);height:var(--height);perspective:1000px}
    .flip-box-inner{
      width:100%;height:100%;position:relative;transform-style:preserve-3d;
      animation: spin var(--speed) linear infinite;
    }
    .face{
      position:absolute;inset:0;
      display:flex;align-items:center;justify-content:center;
      backface-visibility:hidden;
      border-radius:18px;
      background:transparent; /* brak tła */
      font-size:3rem;
      font-weight:900;
      color:var(--neon-color);

      /* neon glow */
      text-shadow:
        0 0 10px var(--neon-color),
        0 0 20px var(--neon-color),
        0 0 40px var(--neon-color),
        0 0 80px var(--neon-color);

      /* czarny kontur liter */
      -webkit-text-stroke: 2px #000;
      text-stroke: 2px #000;
    }
    .back{transform:rotateY(180deg)}
    @keyframes spin{from{transform:rotateY(0deg)}to{transform:rotateY(360deg)}}
    /* puls neon */
    .face{animation:neonPulse 2s infinite alternate}
    @keyframes neonPulse{
      0%{text-shadow:0 0 8px var(--neon-color),0 0 18px var(--neon-color)}
      100%{text-shadow:0 0 20px var(--neon-color),0 0 55px var(--neon-color)}
    }
  </style>
</head>
<body>
  <div class="wrap">
    <div class="flip-box">
      <div class="flip-box-inner">
        <div class="face front">KLIMAKSZEF</div>
        <div class="face back">TWITCH</div>
      </div>
    </div>
  </div>
</body>
</html>
