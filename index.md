---
title: Grotjahn Lab @ Scripps
layout: parallax_lead
group: home
banner: static/img/banners/morphometrics_1.png
---


The Grotjahn Lab connects molecular structure with cellular context to study how mitochondria remodel their shape, composition, and function in response to changing cellular demands and stressors. Our goal is to uncover fundamental mechanisms of mitochondrial adaptation that could inform new therapeutic strategies for disease.


Interactive Surface Morphometrics Visualization 
[Surface morphometrics](https://github.com/GrotjahnLab/surface_morphometrics) is a computational framework originally developed in the Grotjahn Lab and now maintained in collaboration with the [Barad Lab](https://baradlab.com/). Surface morphometrics converts the complex 3D membranes captured by cryo-electron tomography into quantitative maps of cellular architecture. These measurements reveal how membrane shape, spacing, and organization change across biological conditions.
Slide the vertical lines to reveal different membrane properties.
<style>
  .image-slider-wrapper {
    max-width: 800px;
    margin: 40px auto;
  }

  .image-slider-figure {
    position: relative;
    width: 100%;
    padding-bottom: 100%; /* 1:1 aspect ratio */
    border: 1px solid #ccc;
    overflow: hidden;
    background: #fff;
  }

  .image-slider-figure > img {
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

  .image-mask {
    position: absolute;
    top: 0;
    bottom: 0;
    overflow: hidden;
    z-index: 2;
  }

  .image-mask img {
    position: absolute;
    top: 0;
    height: 100%;
    object-fit: contain;
    user-select: none;
    pointer-events: none;
  }
  
  #imageMask2 {
    left: 0;
  }
  
  #imageMask2 img {
    left: 0;
  }
  
  #imageMask1 {
    right: 0;
  }
  
  #imageMask1 img {
    right: 0;
  }

  .slider-handle {
    position: absolute;
    top: 0;
    bottom: 0;
    width: 4px;
    background: #333;
    cursor: ew-resize;
    z-index: 30;
  }

  .slider-handle::after {
    content: '';
    position: absolute;
    top: 50%;
    left: -6px;
    width: 16px;
    height: 16px;
    background: #333;
    border-radius: 50%;
    transform: translateY(-50%);
  }
</style>

<div class="image-slider-wrapper">
  <div class="image-slider-figure" id="sliderFigure">
    <!-- Base image (leftmost) -->
    <img src="/static/img/morph/thickness_MIM019_2_lam6_ts_003.svg" alt="Thickness">

    <!-- Middle image (between sliders) -->
    <div class="image-mask" id="imageMask2">
      <img src="/static/img/morph/OMM_distace_MIM019_2_lam6_ts_003.svg" alt="OMM Distance" id="middleImg">
    </div>

    <!-- Right image (rightmost) -->
    <div class="image-mask" id="imageMask1">
      <img src="/static/img/morph/curvedness_MIM019_2_lam6_ts_003.svg" alt="Curvedness" id="rightImg">
    </div>

    <!-- Slider handles -->
    <div class="slider-handle" id="leftSlider"></div>
    <div class="slider-handle" id="rightSlider"></div>
  </div>
</div>

<script>
(function() {
  const figure = document.getElementById('sliderFigure');
  const leftSlider = document.getElementById('leftSlider');
  const rightSlider = document.getElementById('rightSlider');
  const mask2 = document.getElementById('imageMask2');
  const mask1 = document.getElementById('imageMask1');
  const middleImg = document.getElementById('middleImg');
  const rightImg = document.getElementById('rightImg');

  let leftPos = 0.33;
  let rightPos = 0.67;

  function updateSliders() {
    const w = figure.clientWidth;
    const leftPx = leftPos * w;
    const rightPx = rightPos * w;

    leftSlider.style.left = leftPx + 'px';
    rightSlider.style.left = rightPx + 'px';

    // Middle mask shows between left and right sliders
    mask2.style.left = leftPx + 'px';
    mask2.style.width = (rightPx - leftPx) + 'px';
    middleImg.style.left = (-leftPx) + 'px';
    middleImg.style.width = w + 'px';

    // Right mask shows from right slider to end
    mask1.style.left = rightPx + 'px';
    mask1.style.width = (w - rightPx) + 'px';
    rightImg.style.left = (-rightPx) + 'px';
    rightImg.style.width = w + 'px';
  }

  function makeDraggable(handle, isLeft) {
    let isDragging = false;

    function onMove(e) {
      if (!isDragging) return;
      
      const rect = figure.getBoundingClientRect();
      let x = (e.clientX - rect.left) / rect.width;
      x = Math.max(0, Math.min(1, x));

      if (isLeft) {
        leftPos = Math.min(x, rightPos - 0.05);
      } else {
        rightPos = Math.max(x, leftPos + 0.05);
      }
      updateSliders();
    }

    function onEnd() {
      isDragging = false;
      document.removeEventListener('mousemove', onMove);
      document.removeEventListener('mouseup', onEnd);
      document.removeEventListener('touchmove', onMove);
      document.removeEventListener('touchend', onEnd);
    }

    function onStart(e) {
      isDragging = true;
      e.preventDefault();
      document.addEventListener('mousemove', onMove);
      document.addEventListener('mouseup', onEnd);
      document.addEventListener('touchmove', onMove);
      document.addEventListener('touchend', onEnd);
    }

    handle.addEventListener('mousedown', onStart);
    handle.addEventListener('touchstart', onStart);
  }

  makeDraggable(leftSlider, true);
  makeDraggable(rightSlider, false);

  updateSliders();
  window.addEventListener('resize', updateSliders);
})();
</script>

