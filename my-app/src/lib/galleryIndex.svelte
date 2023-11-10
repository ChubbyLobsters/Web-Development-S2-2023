<script>
    // Import the onMount function from Svelte
    import { onMount } from 'svelte';
  
    // Define the images and alt text as props
    export let images = [];
    export let altText = 'images for gallery';
  
    // Function to preload images
    async function preloadImages(images) {
      // Loop through the provided image URLs
      for (const image of images) {
        const imgElement = new Image();
  
        // Set the source of the image element
        imgElement.src = image;
  
        // Wait for the image to load
        await new Promise((resolve) => {
          imgElement.onload = resolve;
        });
      }
    }
  
    // Call the preloadImages function when the component is mounted
    onMount(() => {
      preloadImages(images);
    });
  </script>
  
  <div class="gallery">
    {#each images as image (image)}
      <!-- Display each image with alt text -->
      <img src={image} alt={altText} />
    {/each}
  </div>
  
  <style>
    .gallery {
       /* Style the gallery container */
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
      padding: 0 35px;
    }
  
    .gallery img {
       /* Style each image within the gallery */
      width: 30%; /* Set a fixed width for all images */
      height: auto; /* Maintain aspect ratio */
      object-fit: cover; /* Crop images to fit within their fixed dimensions */
    }
  </style>
