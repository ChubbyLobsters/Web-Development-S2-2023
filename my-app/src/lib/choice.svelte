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

<style>
  main {
    text-align: center;
  }

  .button-section {
    display: flex;
    justify-content: center;
  }

  .image-box {
    margin: 60px;
    text-decoration: none;
    display: inline-block;
  }

  .image-box:hover,
  .image-box:focus {
    opacity: 0.7;
  }

  .image-box.pick:hover,
  .image-box.pick:focus {
    opacity: 1;
  }

  .image-box img {
    width: 440px;
    height: 680px;
  }

  .image-box.pick img {
    width: 280px;
    height: 600px;
  }

  .image-box:last-child img {
    width: 390px;
    height: 580px;
    margin-top: 60px;
  }
</style>

<main>
  <div class="button-section">
    <div class="image-box" on:mouseover={handleHover1} on:mouseout={handleUnhover1} on:focus={handleFocus1} on:blur={handleBlur1} role="button">
      <a href={route1}>
        <img src={isHovered1 ? "images/main/choiceHover.jpg" : imageSrc1} alt="Choice" tabindex="0" aria-label="Choice" />
      </a>
    </div>
    
    <div class="image-box pick">
      <img src={imageSrc2} alt="Pick" />
    </div>
    <div class="image-box" on:mouseover={handleHover3} on:mouseout={handleUnhover3} on:focus={handleFocus3} on:blur={handleBlur3} role="button">
      <a href={route2}>
        <img src={isHovered3 ? "images/main/fateHoverd.jpg" : imageSrc3} alt="Fate" tabindex="0" aria-label="Fate" />
      </a>
    </div>
    
  </div>
</main>
