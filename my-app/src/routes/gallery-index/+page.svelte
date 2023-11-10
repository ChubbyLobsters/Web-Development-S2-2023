<script>
  var words = [
    { text: "Elysian Echoes: Chronicles of the Fallen Seraph", route: "/Elysian", imgSrc: "images/index/one.jpg", imgHoverSrc: "images/index/oneHoverd.jpg" },
    { text: "BLOOD LUST DEATH", route: "/BLD", imgSrc: "images/index/two.jpg", imgHoverSrc: "images/index/twoHoverd.jpg" },
    { text: "幻想的なカオス (Gensō-tekina Kaosu)", route: "/Genso", imgSrc: "images/index/three.jpg", imgHoverSrc: "images/index/threeHoverd.jpg" },
    { text: "Lumina Noctis: Ethereal Rhapsodies of Psychedelic Dreamscape", route: "/Lumina", imgSrc: "images/index/four.jpg", imgHoverSrc: "images/index/fourHoverd.jpg" },
  ];

  var currentHoverRoute = "";

  function handleImageHover(route) {
    currentHoverRoute = route;
  }
</script>

<div class="centered-words">
  <!-- Add an image to the top center -->
  <img src="images/index/top.jpg" alt="Top Center Image" class="top-center-image">
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

<div class="centered-images">
  <!-- Make the bottom image less stretched -->
  <img src="images/index/bottom.jpg" alt="Bottom Image" class="bottom-image">
</div>

<style>
  .centered-words {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-bottom: 20px;
    margin-top: 20px;
  }

  .centered-words ul {
    list-style: none;
    padding: 0;
  }

  .word {
    transition: color 0.3s;
    padding: 20px 0;
    font-weight: bold;
    display: inline-block;
    position: relative;
    margin: 20px;
    color: transparent;
    cursor: pointer;
  }

  .word img {
    max-width: 100%;
    display: block;
    transition: transform 0.3s;
  }

  .word:hover img {
    transform: scale(1.1);
  }

  .centered-images {
    display: flex;
    align-items: center;
    justify-content: center; /* Center horizontally and vertically */
    height: 100px; /* Make it take the full height of the viewport */
    padding-bottom: 50px;
  }

  .centered-images img {
    max-width: 30%; /* Adjust the maximum width */
    max-height: auto; /* Adjust height based on the image's aspect ratio */
  }

  .top-center-image {
    max-width: 40%;
    padding-bottom: 30px;
  }

  @media (max-width: 768px) {
    .centered-words {
      padding: 20px;
    }

    .word {
      padding: 10px 0;
      margin: 10px;
    }

    .word img {
      max-width: 80%;
    }

    .centered-images img {
      max-height: 200px;
    }
  }
</style>
