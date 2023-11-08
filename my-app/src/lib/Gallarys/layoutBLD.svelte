<script>
    let images = [
      'images/bld/BLD1.png',
      'images/bld/BLD12.png',
      'images/bld/BLD2.png',
      'images/bld/BLD3.png',
      'images/bld/BLD4.png',
      'images/bld/BLD5.png',
    ];
  
    // Function to preload images
    async function preloadImages() {
      for (const image of images) {
        const imgElement = new Image();
        imgElement.src = image;
        await new Promise((resolve) => {
          imgElement.onload = resolve;
        });
      }
    }
  
    preloadImages();
  </script>
  
  <div class="gallery">
    {#each images as image (image)}
      <img src={image} alt="Descriptive Alt Text" />
    {/each}
  </div>
  

  <style>
    .gallery {
      display: flex;
      flex-wrap: wrap;
      justify-content: center; 
      gap: 10px;
      padding: 0 35px; 
    }
  
    .gallery img {
      width: 30%; 
      height: auto;
    }
  </style>
