---
title: Grotjahn Lab Media
layout: parallax
group: media
banner: /static/img/banners/media.png
---

# Public Lectures, Podcasts, Interviews, and Workshops
### 2024 [Front Row Lecture](https://frontrow.scripps.edu/lectures/grotjahn/)
The mitochondria are well known for being cellular “powerhouses,” given their important role in energy generation. Yet, emerging research is now suggesting these organelles also play a key role as the stress-sensors for the cell. In this free Front Row lecture, Scripps Research assistant professor Danielle Grotjahn explored how mitochondria change shape in response to different genetic and environmental stressors. By harnessing cutting-edge imaging technologies to examine mitochondria in these never-before-seen-ways, Grotjahn is revealing how these organelles can predict overall cellular health and even disease, including neurodegenerative disorders and cancer.
<iframe width="921" height="518" src="https://www.youtube.com/embed/WxpCcvpTyBY" title="Peering into the mitochondria to reveal cellular stress and disease" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### 2023 [Decoding the mitochondria with Dr. Danielle Grotjahn](https://www.thermofisher.com/blog/atomic-resolution/mitochondrial-dysfunction-cryo-electron-tomography/)
Dr. Danielle Grotjahn, Assistant Professor at Scripps Research Institute, discusses how cryo-electron tomography is a powerful tool that is advancing our understanding of the mitochondria and ultimately human health.
<iframe width="668" height="376" src="https://www.youtube.com/embed/MdAxI6PZWmw" title="Dr Danielle Grotjahn how cryo electron tomography is advancing our understanding of cellular biology" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### 2023 [Science Changing Life Podcast](https://soundcloud.com/sciencechanginglife/episode-38-danielle-grotjahn-what-mitochondria-tell-us-about-disease-stress-and-cell-death) 
Are the mitochondria truly the powerhouses of the cell? In this episode, assistant professor Danielle Grotjahn shares why she thinks “the stress sensors of the cell” may be a more appropriate name for this cellular organelle–and more. Dr. Grotjahn works in the Department of Integrative Structural and Computational Biology at Scripps Research, where her lab is answering how mitochondrial networks change shape in response to genetic, pharmacological or environmental stress. Listen as we talk about the links between mitochondrial dysfunction and disease, cell death, and the cutting-edge imaging technologies that are enabling Grotjahn and her team to peer into the mysteries of the mitochondria.
<iframe width="668" height="376" src="https://www.youtube.com/embed/lPcYv5FIbdk?list=PLYsfxL6EAopP19HhAkc2vOqZ_QNTiUh0a" title="Episode 38 – Danielle Grotjahn: What mitochondria tell us about disease, stress and cell death" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### 2019 [Scripps Research blog](https://www.scripps.edu/news-and-events/blog/) [Part 1](https://www.scripps.edu/news-and-events/blog/read/index.php?id=555) and [Part 2](https://www.scripps.edu/news-and-events/blog/read/index.php?id=556) A conversation with: Danielle Grotjahn, PhD, Scripps Research Fellow
[![ScrippsBlog](/static/img/logo/scrippsblog.jpg)](https://www.scripps.edu/news-and-events/blog/read/index.php?id=555)
### 2018 [Radiobio interviews Dr. Danielle Grotjahn](https://soundcloud.com/user-386034408/radiobio-interviews-dr-danielle-grotjahn)
We often imagine a cell as a large balloon filled with jelly, but really it is more like a large city. Packages need to go from one place to the other in an organized fashion as to not disrupt other processes. For example, when we need an item, we go to the store or click away on retail websites, but how do these items find their way to the retail place or our house? There are vehicles on roads and highways that are utilized for distribution. Much like the infrastructure that we use everyday to move cargo around our cities, the cell has its own system to deliver goods from one place to another. What are the 18 wheelers of the cell, how do they move such important packages, and how do they know where to go? Cytoplasmic dynein is a protein complex that transports molecular cargo along and plays a key role in the intracellular trafficking network. Dr. Danielle Grotjahn utilizes specialized imaging techniques to study these structures and the function of motor proteins.
<iframe width="668" height="376" src="https://www.youtube.com/embed/rIz21VboAP8" title="[Audio] Radiobio interviews Dr. Danielle Grotjahn about visualizing motor proteins in cells" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<body>
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
    <img src="/static/img/morph/thickness_MIM019_2_lam6_ts_003.svg" alt="Image 3">

    <!-- Image 2 (between sliders) -->
    <div class="mask" id="mask2">
      <img src="/static/img/morph/OMM_distace_MIM019_2_lam6_ts_003.svg" alt="Image 2">
    </div>

    <!-- Image 1 (right of right slider) -->
    <div class="mask" id="mask1">
      <img src="/static/img/morph/curvedness_MIM019_2_lam6_ts_003.svg" alt="Image 1">
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

