---
title: Grotjahn Lab @ Scripps
layout: parallax_lead
group: home
banner: static/img/banners/morphometrics_1.png
---


The Grotjahn Lab connects molecular structure with cellular context to study how mitochondria remodel their shape, composition, and function in response to changing cellular demands and stressors. Our goal is to uncover fundamental mechanisms of mitochondrial adaptation that could inform new therapeutic strategies for disease.

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Surface Colormap Comparison</title>

<style>
  body {
    font-family: system-ui, sans-serif;
  }

  .wrapper {
    width: 720px;
    margin: 30px auto;
  }

  .figure {
    position: relative;
    width: 100%;
    aspect-ratio: 1 / 1;
    border: 1px solid #ccc;
    overflow: hidden;
    background: #fff;
  }

  .figure > img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: contain;
    user-select: none;
    pointer-events: none;
    z-index: 1;
  }

  .mask {
    position: absolute;
    top: 0;
    bottom: 0;
    overflow: hidden;
    z-index: 2;
  }

  .mask img {
    position: absolute;
    top: 0;
    width: 720px;
    height: 720px;
    object-fit: contain;
    user-select: none;
    pointer-events: none;
  }
  
  #mask2 img {
    left: calc(-1 * var(--mask2-left, 0px));
  }
  
  #mask1 img {
    left: calc(-1 * var(--mask1-left, 0px));
  }

  .handle {
    position: absolute;
    top: 0;
    bottom: 0;
    width: 4px;
    background: #111;
    cursor: ew-resize;
    z-index: 20;
  }

  .handle::after {
    content: '';
    position: absolute;
    top: 50%;
    left: -6px;
    width: 16px;
    height: 16px;
    background: #111;
    border-radius: 50%;
    transform: translateY(-50%);
  }

  .snap-line {
    position: absolute;
    top: 0;
    bottom: 0;
    width: 1px;
    background: rgba(0,0,0,0.15);
    pointer-events: none;
  }

  .region-label {
    position: absolute;
    bottom: 8px;
    padding: 3px 6px;
    background: rgba(255,255,255,0.9);
    font-size: 0.8rem;
    border-radius: 4px;
    z-index: 25;
  }

  .label-left   { left: 8px; }
  .label-middle { left: 50%; transform: translateX(-50%); }
  .label-right  { right: 8px; }
</style>
</head>

<body>

<div class="wrapper">

  <div class="figure" id="figure">

    <!-- Image 3 (left of left slider) -->
    <img src="img/morph/thickness_MIM019_2_lam6_ts_003.svg" alt="Image 3">

    <!-- Image 2 (between sliders) -->
    <div class="mask" id="mask2">
      <img src="img/morph/OMM_distace_MIM019_2_lam6_ts_003.svg" alt="Image 2">
    </div>

    <!-- Image 1 (right of right slider) -->
    <div class="mask" id="mask1">
      <img src="img/morph/curvedness_MIM019_2_lam6_ts_003.svg" alt="Image 1">
    </div>

    <!-- Handles -->
    <div class="handle" id="leftHandle"></div>
    <div class="handle" id="rightHandle"></div>

  </div>

</div>

<script>
  const figure = document.getElementById('figure');
  const leftHandle = document.getElementById('leftHandle');
  const rightHandle = document.getElementById('rightHandle');
  const mask2 = document.getElementById('mask2');
  const mask1 = document.getElementById('mask1');

  let leftX = 1/3;
  let rightX = 2/3;

  function update() {
    const w = figure.clientWidth;

    const leftPx = leftX * w;
    const rightPx = rightX * w;

    leftHandle.style.left = leftPx + 'px';
    rightHandle.style.left = rightPx + 'px';

    // Image 2 shows between the two sliders
    mask2.style.left = leftPx + 'px';
    mask2.style.width = (rightPx - leftPx) + 'px';
    mask2.style.setProperty('--mask2-left', leftPx + 'px');

    // Image 1 shows to the right of the right slider
    mask1.style.left = rightPx + 'px';
    mask1.style.width = (w - rightPx) + 'px';
    mask1.style.setProperty('--mask1-left', rightPx + 'px');
  }

  function drag(handle, isLeft) {
    function move(e) {
      const rect = figure.getBoundingClientRect();
      let x = (e.clientX - rect.left) / rect.width;
      x = Math.max(0, Math.min(1, x));

      if (isLeft) {
        leftX = Math.min(x, rightX - 0.05);
      } else {
        rightX = Math.max(x, leftX + 0.05);
      }
      update();
    }

    function stop() {
      document.removeEventListener('mousemove', move);
      document.removeEventListener('mouseup', stop);
    }

    handle.addEventListener('mousedown', () => {
      document.addEventListener('mousemove', move);
      document.addEventListener('mouseup', stop);
    });
  }

  drag(leftHandle, true);
  drag(rightHandle, false);

  update();
  
  // Update on window resize
  window.addEventListener('resize', update);
</script>

</body>
</html>
