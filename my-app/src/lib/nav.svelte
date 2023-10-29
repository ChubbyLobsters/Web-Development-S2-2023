<script>
  function scrollIntoView({ target }) {
    const el = document.querySelector(target.getAttribute('href'));
    el.scrollIntoView({
      behavior: 'smooth'
    });
  }
</script>

<header style="height: 220px;"> 
  <div class="navWrapper" id="home">
    <div class="clearfix">
      <nav class="mainNav clearfix">
        <nav>
          <ul class="left-links"> 
            <li><a href="/">Home</a></li>
            <li><a href="/gallery-index">Gallery</a></li>
          </ul>
          <div class="logo-container">
            <img class="logo" src="logo.jpg" alt="Logo" />
          </div>
          <ul class="right-links"> 
            <li><a href="#section-1" on:click|preventDefault={scrollIntoView}>About</a></li>
            <li><a href="#section-2" on:click|preventDefault={scrollIntoView}>Contact</a></li>
          </ul>
        </nav>
      </nav>
    </div>
  </div>
</header>

<style>
  .clearfix:after {visibility: hidden; display: block; font-size: 0; content: " "; clear: both; height: 0; }

  * { -moz-box-sizing: border-box; -webkit-box-sizing: border-box; box-sizing: border-box; }

  .logo {
    max-width: 160px;
    margin-top: 30px;
  }

  nav {
    padding: 0;
    margin: 0;
    width: 100%;
    height: 50px;
    display: flex; 
    justify-content: space-between; 
    align-items: center;
  }

  header nav ul {
    padding: 0;
    margin: 0;
    background: rgb(255, 255, 255);
    list-style: none; 
  }

  header nav ul li {
    margin: 0;
    display: inline;
    text-align: center;
  }

  header nav ul li:hover {
    background: none;
    transform: scale(1.2);
  }

  header nav ul li a {
    text-decoration: none;
    padding: 15px 20px;
    color: #000000;
    margin: 0;
    display: inline-block;
    text-transform: uppercase;
    font-family: 'Quicksand', sans-serif;
    font-size: 1rem;
  }

  header nav ul li a:focus {
    outline: none;
  }

  header {
    background-color: rgb(255, 255, 255);
    margin-bottom: 20px;
    position: relative;
  }

  .left-links {
    float: left;
  }

  .right-links {
    float: right; 
  }
</style>
