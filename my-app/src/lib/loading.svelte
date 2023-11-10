<script>
  let isLoading = true;

  // Simulate loading for demonstration purposes
  setTimeout(() => {
    isLoading = false;
  }, 7000);
</script>

{#if isLoading}
  <div id="loading-overlay" class="fade-in-out">
    <img src="images/main/loading.gif" alt="Loading Animation" class="centered-image" />
  </div>
{/if}

<style>
  #loading-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 9999;
    animation: fadeInOut 3.5s linear forwards; 
    pointer-events: none; 
  }

  .centered-image {
    width: 250px;
    height: auto; 
    opacity: 0;
    animation: fadeInImage 2.5s linear forwards; 
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

  /* CSS animation for overlay fade-in and smooth fade-out */
  @keyframes fadeInOut {
    0% {
      opacity: 1;
    }
    
    100% {
      opacity: 0; /* Gradually go to full transparency */
    }
  }
</style>
