<script>
  let bio = "I am Cameron Yeoman, the enigmatic night crawler of street art and the conductor of the underground music symphony. In the moon's tender embrace, I don my cloak of mystery and step into the hidden canvas of the city's streets, where my artistic spirit awakens with every step. My presence in the community is like a whisper in the wind, a secret shared only among the nocturnal creatures of creativity, yet unknown to even my closest friends and family."

  let goal = "My ultimate ambition dances on the edge of whimsy and wonder. As the night's patron of unconventional arts, I aspire to one day craft prosthetics that are a fusion of art and function, like extensions of the human imagination. My dreams extend to the creation of enchanting body modding devices, where reality and fantasy intertwine to sculpt the human form into a canvas of self-expression."

  let signatures = "WomenEatersOffical, MrWildFire, CY, ForGottenDreams. As forever burning citys to the ground in inspiration."  // holding data for paragraphs will simplify later

  let imageUrl1 = "images/main/portrait.jpg";
  let imageUrl2 = "images/main/scribble1.jpg";
</script>

<div class="container">
  <div class="compact-section">
      <div class="image">
          <img src={imageUrl1} alt="Image" />
      </div>
      <div class="content">
          <p><strong>{bio}</strong></p>
      </div>
  </div>

  <div class="additional-image">
      <img src={imageUrl2} alt="Additional Image" />
  </div>

  <div class="goal-section">
      <div class="content">
          <p><strong>{goal}</strong></p>
      </div>
  </div>

  <div class="signatures-section">
      <div class="content">
          <p>{signatures}</p>
      </div>
  </div>
</div>

<style>
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    max-width: 50%;
    padding: 0 20px;
  }

  .compact-section, .goal-section, .signatures-section {
    width: 100%;
    padding: 10px;
    box-sizing: border-box;
    text-align: center;
    padding-bottom: 35px;
  }

  .compact-section {
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 8px;
  }

  .image {
    flex: 1;
    max-width: 40%; /* Adjust the maximum width of the image */
  }

  .image img {
    max-width: 100%; /* Ensure the image inside the .image container scales */
    height: auto;
  }

  .additional-image {
    width: 25%;
    text-align: center;
    margin-top: 10px;
  }

  .additional-image img {
    max-width: 100%; /* Ensure the additional image inside the .additional-image container scales */
    height: auto;
  }

  .content {
    flex: 2;
  }

  p {
    font-size: 12px;
    font-family: Arial, sans-serif;
    line-height: 1.5;
    font-weight: bold;
    margin: 10px 0;
  }

  @media screen and (max-width: 935px) {
    p {
      font-size: 9px;
    }
  }

  @media screen and (max-width: 768px) {
    p {
      font-size: 7px;
    }
  }

  @media screen and (max-width: 580px) {
    p {
      font-size: 6px;
    }
  }

  @media screen and (max-width: 420px) {
    p {
      font-size: 4px;
    }
  }

  @media screen and (max-width: 320px) {
    p {
      font-size: 3px;
    }
  }
</style>
