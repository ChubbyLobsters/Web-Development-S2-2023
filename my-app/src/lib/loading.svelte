<script>
  let isLoading = true;

  // Simulate loading for demonstration purposes
  setTimeout(() => {
    isLoading = false;
  }, 7000); 
</script>

{#if isLoading}
  <div id="loading-overlay" class="fade-in-out">
    <img src="loading.gif" alt="Loading Animation" class="centered-image" />
  </div>
{/if}

<style>
  #loading-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: white; /* Use a solid white background */
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 9999;
    opacity: 1; /* Initially, the overlay is fully visible */
    animation: fadeInOut 8s linear; 
  }

  .centered-image {
    width: 250px;
    height: auto; /* Maintain aspect ratio */
    opacity: 0; 
    animation: fadeInImage 5s linear; 
    animation-fill-mode: forwards; /* Keeps the final state of opacity */
  }

  /* CSS animation for image fade-in */
  @keyframes fadeInImage {
    0% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }

  /* CSS animation for overlay fade-in and fade-out */
  @keyframes fadeInOut {
    0%, 100% {
      opacity: 1; /* Start and end with full opacity */
    }
    99% {
      opacity: 0; /* Almost immediately go to full transparency */
    }
  }
</style>

