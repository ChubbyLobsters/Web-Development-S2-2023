<script>
  // JavaScript code can be added here if needed
</script>

<header>
  <a href="https://media.senscritique.com/media/000019712106/source_big/Puparia.jpg" id="logo">Logo</a>
</header>

<section id="hero1" class="hero">
  <div class="inner">
    <div class="copy">
      <h1>Blank</h1>
      <p>Blank</p>
    </div>
  </div>
</section>

<section class="content">
  <div class="inner">
    <div class="copy">
      <h1>Blank</h1>
      <p>Blank</p>
    </div>
  </div>
</section>

<section id="hero2" class="hero">
  <div class="inner">
    <div class="copy">
      <h1>Blank</h1>
      <p>Blank</p>
    </div>
  </div>
</section>

<section class="content">
  <div class="inner">
    <div class="copy">
      <h1>Blank</h1>
      <p>Blank</p>
    </div>
  </div>
</section>

<section id="hero3" class="hero">
  <div class="inner">
    <div class="copy">
      <h1>Blank</h1>
      <p>Blank</p>
    </div>
  </div>
</section>

<section class="content">
  <div class="inner">
    <div class="copy">
      <h1>Blank</h1>
      <p>Blank</p>
    </div>
  </div>
</section>

<section id="hero4" class="hero">
  <div class="inner">
    <div class="copy">
      <h1>Blank</h1>
      <p>Blank</p>
    </div>
  </div>
</section>

<style>
  html, body {
    margin: 0;
    padding: 0;
  }

  *, *:after, *:before {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
  }

  header {
    z-index: 1;
    position: fixed;
    width: 100%;
    height: 60px;
    background: rgba(0, 0, 0, 0.1);
  }

  header a {
    color: white;
    background: rgba(0, 0, 0, 0.1);
    display: inline-block;
    padding: 0px 30px;
    height: 60px;
    line-height: 60px;
    text-align: center;
    font-family: 'Roboto Slab', serif;
    text-decoration: none;
    text-transform: uppercase;
    letter-spacing: 2px;
    font-weight: 700;
  }

  .hero,
  .content {
    text-align: center;
    position: relative;
    width: 100%;
  }

  .inner {
    min-height: 600px;
    position: relative;
  }

  .hero .inner {
    background: rgba(0, 0, 0, 0.363) url() repeat;
  }

  .copy {
    position: absolute;
    top: 50%;
    height: 10em;
    margin-top: -5em;
    width: 100%;
  }

  .hero h1,
  .hero p {
    color: #fff;
  }

  .content h1,
  .content p {
    color: #333;
  }

  h1 {
    margin: 0px;
    font-family: 'Roboto Slab', serif;
    font-weight: 400;
    font-size: 32px;
    padding: 0px 20px;
  }

  p {
    font-family: 'Noto Sans', sans-serif;
    font-size: 14px;
    padding: 0px 20px;
  }

  #hero1,
  #hero2,
  #hero3,
  #hero4 {
    background-attachment: fixed;
    background-repeat: no-repeat;
    background-size: cover; /* Use the cover value to fit both width and height */
  }

  #hero1 {
    background-image: url("../lib/titlefix.png");
    height: 100vh; /* Set initial height to full viewport height */
  }

  #hero2 {
    background-image: url("../lib/titlefix.png");
    background-position: center calc(25% + 60px); /* Adjust the value as needed */
  }

  #hero3 {
    background-image: url("../lib/titlefix.png");
    background-position: center calc(50% + 60px); /* Adjust the value as needed */
  }

  #hero4 {
    background-image: url("../lib/titlefix.png");
    background-position: center calc(75% + 60px);
  }

</style>  