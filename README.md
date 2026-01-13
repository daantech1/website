<!DOCTYPE html>
<html lang="nl">
<head>
  <meta charset="UTF-8" />
  <title>Camera Grid - Skiien</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html, body {
      height: 100%;
      overflow: hidden;
    }

    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      background: #020617;
      color: #e5e7eb;
      display: flex;
      flex-direction: column;
    }

    header {
      background: #0f172a;
      border-bottom: 1px solid rgba(148, 163, 184, 0.4);
      padding: 10px 16px;
      display: flex;
      align-items: center;
    }

    main {
      flex: 1;
      min-height: 0;
    }

    .grid-container {
      height: 100%;
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      grid-template-rows: repeat(2, 1fr);
      gap: 2px;
      background: #020617;
    }

    .cam-cell {
      position: relative;
      width: 100%;
      height: 100%;
      overflow: hidden;
      background: black;
    }

    iframe {
      position: absolute;
      inset: 0;
      width: 100%;
      height: 100%;
      border: none;
    }

    /* Fullscreen knop */
    .fullscreen-btn {
      position: absolute;
      top: 8px;
      right: 8px;
      z-index: 10;
      background: rgba(0,0,0,0.6);
      color: white;
      border: none;
      padding: 6px 10px;
      border-radius: 6px;
      cursor: pointer;
      font-size: 12px;
    }

    .fullscreen-btn:hover {
      background: rgba(0,0,0,0.85);
    }

    @media (max-width: 768px) {
      .grid-container {
        grid-template-columns: 1fr;
        grid-template-rows: repeat(4, 1fr);
      }
    }
  </style>
</head>

<body>

  <header>
    <strong>Camera Grid – Skiien</strong>
  </header>

  <main>
    <section class="grid-container">

      <div class="cam-cell">
        <button class="fullscreen-btn">⛶</button>
        <iframe src="https://www.feratel.com/en/webcams/austria/tyrol/finkenberg-penkenjoch"></iframe>
      </div>

      <div class="cam-cell">
        <button class="fullscreen-btn">⛶</button>
        <iframe src="https://www.feratel.com/nl/webcams/oostenrijk/tirol/mayrhofen-penkenbahn"></iframe>
      </div>

      <div class="cam-cell">
        <button class="fullscreen-btn">⛶</button>
        <iframe src="https://www.feratel.com/en/webcams/austria/tyrol/hintertux-gefrorene-wand"></iframe>
      </div>

      <div class="cam-cell">
        <button class="fullscreen-btn">⛶</button>
        <iframe src="https://www.feratel.com/en/webcams/austria/tyrol/hintertux-gefrorene-wand"></iframe>
      </div>

    </section>
  </main>

  <script>
    document.querySelectorAll(".fullscreen-btn").forEach(btn => {
      btn.addEventListener("click", () => {
        const cell = btn.parentElement;
        if (cell.requestFullscreen) {
          cell.requestFullscreen();
        }
      });
    });
  </script>

</body>
</html>
