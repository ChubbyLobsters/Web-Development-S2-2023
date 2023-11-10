<script>
  let route1 = "/gallery-index";
  let route2 = "/card";
  let imageSrc1 = "images/main/choice.jpg";
  let imageSrc2 = "images/main/pick.jpg";
  let imageSrc3 = "images/main/fate.jpg";
  let isHovered1 = false;
  let isHovered3 = false;

  function handleHover1() {
    isHovered1 = true;
  }

  function handleUnhover1() {
    isHovered1 = false;
  }

  function handleFocus1() {
    isHovered1 = true;
  }

  function handleBlur1() {
    isHovered1 = false;
  }

  function handleHover3() {
    isHovered3 = true;
  }

  function handleUnhover3() {
    isHovered3 = false;
  }

  function handleFocus3() {
    isHovered3 = true;
  }

  function handleBlur3() {
    isHovered3 = false;
  }
</script>

<main>
  <div class="button-section">
    <div class="image-box" on:mouseover={handleHover1} on:mouseout={handleUnhover1} on:focus={handleFocus1} on:blur={handleBlur1} role="button" tabindex="0">
      <a href={route1}>
        <img src={isHovered1 ? "images/main/choiceHover.jpg" : imageSrc1} alt="Choice" aria-label="Choice" />
      </a>
    </div>

    <div class="image-box pick">
      <img src={imageSrc2} alt="Pick" />
    </div>

    <div class="image-box" on:mouseover={handleHover3} on:mouseout={handleUnhover3} on:focus={handleFocus3} on:blur={handleBlur3} role="button" tabindex="0">
      <a href={route2}>
        <img src={isHovered3 ? "images/main/fateHoverd.jpg" : imageSrc3} alt="Fate" aria-label="Fate" />
      </a>
    </div>
  </div>
</main>

<style>
  main {
    text-align: center;
    height: 100%;
    margin-bottom: 10px; /* Add margin after the signatures */
  }

  .button-section {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    max-width: 70%;
    margin: 0 auto;
  }

  .image-box {
    text-decoration: none;
    display: inline-block;
    flex: 1;
  }

  .image-box:hover, .image-box:focus {
    opacity: 0.7;
  }

  .image-box img {
    max-width: 90%;
    height: auto;
    transition: all 0.3s ease-in-out;
  }

  .image-box.pick img {
    max-width: 100%;
    max-height: 35%;
    height: auto;
  }

  @media screen and (max-width: 768px) {
    .image-box {
      margin: 10px;
    }

    .image-box img {
      max-width: 80%;
    }
  }

  @media screen and (max-width: 640px) {
    .image-box img {
      max-width: 75%;
      max-height: 80%;
    }
  }

  @media screen and (max-width: 425px) {
    .image-box img {
      max-width: 90%;
      max-height: 90%;
    }
  }

  @media screen and (max-width: 320px) {
    .image-box img {
      max-width: 90%;
      max-height: 90%;
    }
  }
</style>
