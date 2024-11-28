<script>
  let containerWidth = 400; // Anfangsbreite des Containers
</script>

<div class="wrapper">
  <h1>Media Queries vs Container Queries</h1>
  <p class="breakpoints">
    Ziehe den Schieberegler, um die Breite des Containers zu ändern. Beachte die
    Unterschiede zwischen Media Queries und Container Queries!
  </p>

  <!-- Schieberegler zur Änderung der Breite des Containers -->
  <div class="slider">
    <label for="container-width">Container Width: {containerWidth}px</label>
    <input
      id="container-width"
      type="range"
      min="300"
      max="900"
      bind:value={containerWidth}
      style="width: 100%; max-width: 400px; margin-top: 0.5rem;"
    />
  </div>

  <!-- Flexbox-Container für die beiden Container -->
  <div class="container-wrapper">
    <!-- Container mit Media Queries -->
    <div class="container media-query">
      <div class="content">
        <h2>Media Queries</h2>
        <p>Dieses Layout ändert sich basierend auf der Breite des Viewports.</p>

        <!-- Beispielbilder, die sich je nach Breakpoint verändern -->
        <img src="/image1.png" alt="Beispielbild 1" />
        <img src="/image2.png" alt="Beispielbild 2" />

        <p>Zusätzliche Änderungen werden ab bestimmten Breiten aktiv!</p>
      </div>
    </div>

    <!-- Container mit Container Queries -->
    <div class="container" style="--container-width: {containerWidth}px">
      <div class="content">
        <h2>Container Queries</h2>
        <p>
          Dieses Layout zeigt sich dynamisch bei unterschiedlichen
          Container-Breiten.
        </p>

        <!-- Beispielbilder, die sich je nach Breakpoint verändern -->
        <img src="/image1.png" alt="Beispielbild 1" />
        <img src="/image2.png" alt="Beispielbild 2" />

        <p>Zusätzliche Änderungen werden ab bestimmten Breiten aktiv!</p>
      </div>
    </div>
  </div>
</div>

<style>
  @font-face {
    font-display: swap;
    font-family: "Right";
    font-style: normal;
    font-weight: 100 900;
    src: url("./PPRightSerifMono-Variable.woff2") format("woff2-variations");
  }

  .wrapper {
    font-family: sans-serif;
    max-width: 90%;
    margin: auto;
    text-align: center;
    color: #333;
  }

  h1 {
    color: #333;
    font-family: Right;
    font-size: 2rem;
    margin-bottom: 1rem;
  }

  h2 {
    font-family: Right;
  }

  .breakpoints {
    font-size: 0.9rem;
    color: #666;
    margin: 1rem 0;
  }

  .container-wrapper {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    gap: 1rem;
  }

  /* Container-Stile */
  .container {
    border: 2px solid #666;
    padding: 1rem;
    resize: horizontal;
    overflow: auto;
    width: var(--container-width, 400px);
    max-width: 100%;
    container-type: inline-size;
    border-radius: 8px;
    background-color: #ecebe0; /* Standardfarbe */
    transition: all 0.5s ease;
  }

  .container.media-query {
    width: 400px; /* Feste Breite für den Media Query Container */
  }

  /* Inhalt-Stile */
  .content {
    padding: 1rem;
    color: #333;
    font-size: 1rem;
    transition: all 0.3s ease;
  }

  .content img {
    width: 100%;
    max-width: 100px;
    border-radius: 10px;
    margin-top: 1rem;
    transition: opacity 0.5s ease;
  }

  .slider {
    margin-top: 1.5rem;
    margin-bottom: 1.5rem;
  }

  /* Media Queries */
  @media (min-width: 500px) {
    .container.media-query {
      background-color: #ff562c;
      border-color: #ff562c;
      transform: scale(1.05); /* Leichtes Vergrößern */
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    }

    .container.media-query .content {
      padding: 2rem;
      font-size: 1.5rem;
      color: #ff562c;
    }

    .container.media-query .content img {
      width: 100%;
      max-width: 200px;
      border-radius: 10px;
      margin-top: 1rem;
      transition: opacity 0.5s ease;
    }
  }

  @media (min-width: 700px) {
    .container.media-query {
      margin-top: 3.5rem;
      background-color: #ffb84c;
      border-color: #ff562c;
      border-width: 3px;
      border-style: dashed;
      transform: scale(1.1); /* Weitere Vergrößerung */
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
    }

    .container.media-query .content {
      padding: 3rem;
      font-size: 1.8rem;
      color: #7d791f;
    }

    .container.media-query .content img {
      width: 100%;
      max-width: 300px;
      opacity: 1;
    }
  }

  /* Container Queries */
  @container (min-width: 500px) {
    .container:not(.media-query) {
      background-color: #ff562c;
      border-color: #ff562c;
      transform: scale(1.05); /* Leichtes Vergrößern */
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    }

    .container:not(.media-query) .content {
      padding: 2rem;
      font-size: 1.5rem;
      color: #ff562c;
    }

    .container:not(.media-query) .content img {
      width: 100%;
      max-width: 200px;
      border-radius: 10px;
      margin-top: 1rem;
      transition: opacity 0.5s ease;
    }
  }

  @container (min-width: 700px) {
    .container:not(.media-query) {
      background-color: #ffb84c;
      border-color: #ff562c;
      border-width: 3px;
      border-style: dashed;
      transform: scale(1.1); /* Weitere Vergrößerung */
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
    }

    .container:not(.media-query) .content {
      padding: 3rem;
      font-size: 1.8rem;
      color: #7d791f;
    }

    .container:not(.media-query) .content img {
      width: 100%;
      max-width: 300px;
      opacity: 1;
    }
  }
</style>
