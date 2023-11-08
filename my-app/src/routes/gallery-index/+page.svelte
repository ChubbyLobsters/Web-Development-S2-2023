<script>
  // Define an array of words with corresponding routes
  let words = [
    { text: "Elysian Echoes: Chronicles of the Fallen Seraph", route: "/Elysian", imgSrc: "images/index/one.jpg", imgHoverSrc: "images/index/oneHoverd.jpg" },
    { text: "BLOOD LUST DEATH", route: "/BLD", imgSrc: "images/index/two.jpg", imgHoverSrc: "images/index/twoHoverd.jpg" },
    { text: "幻想的なカオス (Gensō-tekina Kaosu)", route: "/Genso", imgSrc: "images/index/three.jpg", imgHoverSrc: "images/index/threeHoverd.jpg" },
    { text: "Lumina Noctis: Ethereal Rhapsodies of Psychedelic Dreamscape", route: "/Lumina", imgSrc: "images/index/four.jpg", imgHoverSrc: "images/index/fourHoverd.jpg" },
  ];
  
  // Store the currently hovered route
  let currentHoverRoute = "";

  // Function to handle image hover
  function handleImageHover(route) {
    currentHoverRoute = route;
  }
</script>

<style>
  /* Center all content and remove the list-style dots */
  .centered-words {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 160vh;
    margin-bottom: 20px;
    margin-top: 20px;
  }

  .centered-words ul {
    list-style: none; /* Remove list-style dots for the entire list */
  }

  .word {
    transition: color 0.3s; /* Smooth transitions */
    padding: 40px 0; /* Add 10px vertical spacing between words */
    font-weight: bold; /* Use a bold font */
    display: inline-block; /* Ensure spacing between words */
    position: relative; /* Required for pseudo-element */
    margin: 20px;
    color: transparent; /* Set the font color to transparent */
    cursor: pointer; /* Change the cursor to a pointer on hover */
  }

  .word img {
    max-width: 100%; /* Ensure the image fits within the container */
    display: block; /* Remove any extra spacing around the image */
    transition: transform 0.3s; /* Add a smooth transform transition */
  }

  /* Change the image source on hover */
  .word:hover img {
    transform: scale(1.1); /* Scale up the image on hover */
    content: attr(data-src);
  }

  /* Adjust the image styling for both top and bottom images */
  .centered-images img {
    width: 40%; /* Adjust the width of the images as needed */
    max-height: 270px;
    margin-top: 20px; /* Add a 20px top margin to the images */
  }

  /* Center the bottom image by using flex properties */
  .centered-images {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  /* Push the top image down */
  .top-image {
    margin-bottom: 20px; /* Adjust this value as needed */
  }
</style>

<!-- Add the top image below the navigation -->
<div class="centered-words">
  <img class="top-image" src="images/index/top.jpg" alt="Top Image">
  <ul>
    {#each words as word (word.route)}
      <li>
        <a href={word.route} class="word" on:mouseenter={() => handleImageHover(word.route)} on:mouseleave={() => currentHoverRoute = ""}>
          <img src={word.route === currentHoverRoute ? word.imgHoverSrc : word.imgSrc} alt={word.text} />
        </a>
      </li>
    {/each}
  </ul>
</div>

<!-- Add the bottom image below the footer -->
<div class="centered-images">
  <img src="images/index/bottom.jpg" alt="Bottom Image">
</div>
