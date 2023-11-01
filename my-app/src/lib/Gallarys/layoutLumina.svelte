<script>
    let images = [
      'Lumina1.jpeg',
      'Lumina2.jpeg',
      'Lumina3.jpeg',
      'Lumina4.jpeg',
      'Lumina5.jpeg',
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
  
<div class="profile-container">
  <div class="center-profile">
    <img src="profile1.png" alt="" class="profile-image" />
    <a href="https://www.instagram.com/stemkun/" class="profile-name">HAKI</a>
  </div>
</div>
  
<div class="gallery">
  {#each images as image (image)}
    <!-- Use an empty alt attribute for gallery images -->
    <img src={image} alt="" />
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
  
  .profile-container {
    width: 100%;
    background-color: white;
    padding: 20px;
    display: flex;
    align-items: center;
    justify-content: center; /* Center horizontally */
    height: 30vh; /* Center vertically using viewport height */
  }
  
  .center-profile {
    display: flex;
    align-items: center;
  }
  
  .profile-image {
    width: 240px;
    height: 180px;
    border-radius: 50%;
    margin-right: 20px;
  }
  
  .profile-name {
    cursor: pointer;
    color: black;
    font-size: 50px;
  }
</style>
