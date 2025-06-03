<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Image Controller</title>
  <style>
    * { box-sizing: border-box; }
    body, html {
      margin: 0; padding: 0; height: 100%; font-family: sans-serif;
    }
    .main {
      display: flex;
      height: 100vh;
    }
    .image-container {
      width: 75%;
      display: flex;
      align-items: center;
      justify-content: center;
      background: #f0f0f0;
      overflow: hidden;
      position: relative;
    }
    #rotatingImage {
      max-width: 100%;
      max-height: 100%;
      transition: transform 0.2s ease;
      transform-origin: center;
      cursor: grab;
      user-select: none;
    }
    .controls {
      width: 25%;
      background: #fff;
      padding: 20px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      align-items: center;
      border-left: 1px solid #ccc;
    }
    .buttons {
      width: 100%;
      display: flex;
      flex-direction: column;
      gap: 10px;
      align-items: center;
    }
    .buttons button {
      padding: 10px;
      font-size: 16px;
      cursor: pointer;
      width: 80%;
    }
    .zoom-controls {
      display: flex;
      gap: 10px;
      justify-content: center;
    }
    .nav-controls {
      display: grid;
      grid-template-columns: 40px 40px 40px;
      gap: 5px;
      justify-content: center;
      margin-top: 10px;
    }
    .nav-controls button {
      padding: 6px;
      font-size: 16px;
      cursor: pointer;
      width: 100%;
    }
    .nav-controls div {
      width: 40px;
      height: 30px;
    }
    #fileInput {
      display: none;
    }
    .thumbnails {
      margin-top: 20px;
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
      justify-content: center;
    }
    .thumbnails img {
      width: 50px;
      height: 50px;
      cursor: pointer;
      border: 2px solid transparent;
    }
    .thumbnails img:hover {
      border-color: #333;
    }
  </style>
</head>
<body>

<div class="main">
  <div class="image-container" id="imageContainer">
    <img id="rotatingImage" src="img.png" alt="Rotating" />
  </div>
  <div class="controls">
    <div class="buttons">
      <button id="rotateLeftBtn">Rotate Left</button>
      <button onclick="stopRotation()">Stop</button>
      <button id="rotateRightBtn">Rotate Right</button>

      <div class="zoom-controls">
        <button onclick="zoomIn()">Zoom +</button>
        <button onclick="zoomOut()">Zoom −</button>
      </div>

      <div class="nav-controls">
        <div></div>
        <button onmousedown="startMove('up')" onmouseup="stopMove()" onmouseleave="stopMove()">↑</button>
        <div></div>

        <button onmousedown="startMove('left')" onmouseup="stopMove()" onmouseleave="stopMove()">←</button>
        <button onclick="resetImage()">R</button>
        <button onmousedown="startMove('right')" onmouseup="stopMove()" onmouseleave="stopMove()">→</button>

        <div></div>
        <button onmousedown="startMove('down')" onmouseup="stopMove()" onmouseleave="stopMove()">↓</button>
        <div></div>
      </div>

      <div class="thumbnails">
		  <img 
			src="https://upload.wikimedia.org/wikipedia/commons/f/f5/%D8%AD%D8%B1%D9%88%D9%81_%D8%A7%D9%84%D9%85%D8%B9%D8%A7%D9%86%D9%8A.svg" 
			onclick="loadThumbnail(this.src)" 
			alt="لوحة حروف المعاني" 
			title="لوحة حروف المعاني"
		  />
		  <img 
			src="https://upload.wikimedia.org/wikipedia/commons/d/d9/%D9%82%D9%88%D8%A7%D8%B9%D8%AF_%D8%B1%D8%B3%D9%85_%D8%A7%D9%84%D9%87%D9%85%D8%B2%D8%A9.svg" 
			onclick="loadThumbnail(this.src)" 
			alt="قواعد رسم الهمزة" 
			title="قواعد رسم الهمزة"
		  />
		  <img 
			src="https://upload.wikimedia.org/wikipedia/commons/c/c3/%D9%82%D9%88%D8%A7%D8%B9%D8%AF_%D8%A7%D9%84%D8%A5%D9%85%D9%84%D8%A7%D8%A1.svg" 
			onclick="loadThumbnail(this.src)" 
			alt="قواعد الإملاء" 
			title="قواعد الإملاء"
		  />
		  <img 
			src="https://upload.wikimedia.org/wikipedia/commons/8/80/%D9%85%D8%B9%D8%A7%D9%84%D9%85_%D8%A7%D9%84%D9%86%D8%AD%D9%88_%D8%A7%D9%84%D8%B9%D8%B1%D8%A8%D9%8A.svg" 
			onclick="loadThumbnail(this.src)" 
			alt="معالم النحو العربي" 
			title="معالم النحو العربي"
		  />
</div>

    </div>

    <div style="width: 100%; margin-top: 20px; text-align: center;">
      <label for="fileInput" style="cursor: pointer; display: inline-block; text-align: center; padding: 10px; border: 1px solid #666; border-radius: 5px;">
        Select Image
      </label>
      <input type="file" id="fileInput" accept="image/*" />
    </div>
  </div>
</div>

<script>
  let rotation = 0;
  let scale = 1;
  let posX = 0;
  let posY = 0;
  let rotateInterval = null;
  let moveInterval = null;
  let currentDirection = null;
  let mouseHold = false;
  let startY = 0;
  let rotateTimeout = null;

  const img = document.getElementById('rotatingImage');
  const container = document.getElementById('imageContainer');
  const fileInput = document.getElementById('fileInput');
  const rotateLeftBtn = document.getElementById('rotateLeftBtn');
  const rotateRightBtn = document.getElementById('rotateRightBtn');

  function updateTransform() {
    img.style.transform = `translate(${posX}px, ${posY}px) rotate(${rotation}deg) scale(${scale})`;
  }

  function startRotation(direction) {
    if (rotateInterval && currentDirection === direction) {
      stopRotation();
      return;
    }
    stopRotation();
    currentDirection = direction;
    rotateInterval = setInterval(() => {
      rotation += (direction === 'left' ? -3 : 3);
      updateTransform();
    }, 50);
  }

  function rotateLeft() {
    startRotation('left');
  }

  function rotateRight() {
    startRotation('right');
  }

  function stopRotation() {
    clearInterval(rotateInterval);
    rotateInterval = null;
    currentDirection = null;
    clearTimeout(rotateTimeout);
    rotateTimeout = null;
  }

  function zoomIn() {
    scale += 0.1;
    updateTransform();
  }

  function zoomOut() {
    scale = Math.max(0.1, scale - 0.1);
    updateTransform();
  }

  function move(direction) {
    const step = 10;
    if (direction === 'up') posY -= step;
    if (direction === 'down') posY += step;
    if (direction === 'left') posX -= step;
    if (direction === 'right') posX += step;
    updateTransform();
  }

  function startMove(direction) {
    move(direction);
    moveInterval = setInterval(() => move(direction), 100);
  }

  function stopMove() {
    clearInterval(moveInterval);
  }

  function resetImage() {
    stopRotation();
    rotation = 0;
    scale = 1;
    posX = 0;
    posY = 0;
    updateTransform();
  }

  function loadThumbnail(src) {
    img.src = src;
    resetImage();
  }

  container.addEventListener('wheel', (e) => {
    e.preventDefault();
    e.deltaY < 0 ? zoomIn() : zoomOut();
  });

  fileInput.addEventListener('change', (e) => {
    const file = e.target.files[0];
    if (!file) return;
    const reader = new FileReader();
    reader.onload = function(event) {
      img.src = event.target.result;
      resetImage();
    };
    reader.readAsDataURL(file);
  });

  rotateLeftBtn.addEventListener('click', rotateLeft);
  rotateRightBtn.addEventListener('click', rotateRight);

  img.addEventListener('mousedown', (e) => {
    if (e.button !== 0) return;
    e.preventDefault();

    if (rotateInterval) {
      stopRotation();
      return;
    }

    mouseHold = true;
    startY = e.clientY;
  });

  window.addEventListener('mouseup', (e) => {
    if (e.button !== 0) return;
    mouseHold = false;
  });

  img.addEventListener('mousemove', (e) => {
    if (!mouseHold) return;

    const deltaY = e.clientY - startY;

    if (Math.abs(deltaY) < 10) return;

    if (rotateInterval) return;

    if (deltaY < 0) {
      startRotation('left');
      rotateTimeout = setTimeout(stopRotation, 2000);
    } else if (deltaY > 0) {
      startRotation('right');
      rotateTimeout = setTimeout(stopRotation, 2000);
    }

    mouseHold = false;
  });

  updateTransform();
</script>

</body>
</html>
