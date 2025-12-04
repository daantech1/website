<!DOCTYPE html>
<html lang="nl">
<head>
  <meta charset="UTF-8">
  <title>Utrecht CS Jaarbeursplein ⇄ Kanaleneiland Zuid + Bussen De Geer</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <style>
    body {
      font-family: Arial, sans-serif;
      background: #111;
      padding: 20px;
      color: #ffeb3b;
      overflow-x: hidden;
    }

    .box-yellow {
      border: 4px solid #ffeb3b;
      padding: 20px;
      border-radius: 10px;
      background: #222;
      max-width: 1000px;
      margin: auto;
      color: #ffeb3b;
    }

    h2 {
      text-align: center;
      margin-top: 0;
    }

    iframe {
      width: 100%;
      height: 650px;
      border: 0;
      border-radius: 8px;
      background: #000;
    }

    .box-blue {
      border: 4px solid #4da6ff;
      padding: 20px;
      border-radius: 10px;
      background: #002b57;
      max-width: 1000px;
      margin: 40px auto 0;
      color: white;
    }

    .box-blue h2 {
      color: #4da6ff;
      margin-top: 0;
      text-align: center;
    }

    iframe.bus {
      width: 100%;
      height: 350px;
      border: 0;
      border-radius: 8px;
      background: #000;
      margin-top: 15px;
    }

    /* TREINEN */
    .train-zone {
      width: 100%;
      margin-top: 50px;
      position: relative;
      height: 200px;
    }

    .train1 {
      position: absolute;
      bottom: 0;
      width: 320px;
      z-index: 1;
      animation: train-left 20s linear infinite;
    }

    .train2 {
      position: absolute;
      bottom: 80px;
      width: 320px;
      z-index: 1;
      animation: train-right 20s linear infinite;
    }

    @keyframes train-left {
      0%   { left: 120%; }
      100% { left: -350px; }
    }

    @keyframes train-right {
      0%   { left: -350px; }
      100% { left: 120%; }
    }

    /* POLITIEAUTO – blijft nu OP ÉÉN LIJN STAAN */
    .police-container {
      width: 100%;
      height: 120px;
      position: relative;   /* niet meer vast aan het scherm */
      margin-top: 40px;
      overflow: hidden;
    }

    .police {
      position: absolute;
      bottom: 20px;
      width: 230px;
      z-index: 10;
      animation: police-fast 12s linear infinite;
    }

    @keyframes police-fast {
      0%   { left: 120%; }
      100% { left: -400px; }
    }

    .footer-text {
      text-align: center;
      color: #fff;
      margin-top: 15px;
      font-size: 1rem;
      opacity: 0.8;
    }
  </style>
</head>
<body>

<!-- GELE TRAMSECTIE -->
<div class="box-yellow">
  <h2>Utrecht CS Jaarbeursplein ⇄ Kanaleneiland Zuid (Tram 20 & 21)</h2>
  <iframe
    src="https://drgl.nl/stop/NL:S:50000180"
    title="Tram 20/21 – Utrecht CS Jaarbeurszijde (H1 & H2)">
  </iframe>
</div>

<!-- BLAUWE BUSSECTIE -->
<div class="box-blue">
  <h2>Bussen De Geer → Utrecht CS</h2>
  <iframe
    class="bus"
    src="https://drgl.nl/stop/NL:S:50690180"
    title="Bussen De Geer → Utrecht CS">
  </iframe>
</div>

<!-- TREINEN -->
<div class="train-zone">

  <img class="train1"
       src="https://uploads-eu-west-1.insided.com/ns-nl/attachment/6736ca8b-a9d6-4e38-82a9-e01fcc1d83dd.png"
       alt="Trein rechts naar links">

  <img class="train2"
       src="https://uploads-eu-west-1.insided.com/ns-nl/attachment/05fdb9c6-8a0b-4a75-80cd-42104569dcf9.png"
       alt="Trein links naar rechts">

</div>

<!-- POLITIEAUTO STAAT NU VAST OP EEN LIJN -->
<div class="police-container">
  <img class="police"
       src="https://www.publicdomainpictures.net/pictures/450000/nahled/auto-politiewagen-volkswagen.png"
       alt="Politie Auto">
</div>

<div class="footer-text">
  Gemaakt door Daan Verburg
</div>

</body>
</html>
