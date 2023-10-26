<script>
	let isLoading = true;
  
	// Simulate loading for demonstration purposes
	setTimeout(() => {
	  isLoading = false;
	}, 3000); 
  </script>


   {#if isLoading}
   <div id="loading-screen" class="fade-in-out">
	 <img src="loading.gif" alt="Loading Animation" class="centered-image" />
   </div>
 {/if}
 

  <style>
	#loading-screen {
	  position: fixed;
	  top: 0;
	  left: 0;
	  width: 100%;
	  height: 100%;
	  background-color: rgba(255, 255, 255, 1); /* Start with solid white background */
	  display: flex;
	  align-items: center;
	  justify-content: center;
	  z-index: 9999;
	  opacity: 0; /* Start with 0 opacity */
	  animation: fadeInOut 3s linear; /* 3 seconds duration */
	}
  
	.centered-image {
	  width: 250px;
	  height: auto; /* Maintain aspect ratio */
	}
  
	/* CSS animations to fade in and out */
	@keyframes fadeInOut {
	  0%, 100% {
		opacity: 0; /* Start and end with 0 opacity */
	  }
	  25%, 75% {
		opacity: 1; /* Fade in during these periods */
	  }
	  100% {
		opacity: 0; /* Fade out at the end */
	  }
	}
  </style>
  
 