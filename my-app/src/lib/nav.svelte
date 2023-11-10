<script>
  // JavaScript function to scroll smoothly to a section
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
            <!-- Navigation links on the left side -->
            <li><a href="/">Home</a></li>
            <li><a href="/gallery-index">Gallery</a></li>
          </ul>
          <div class="logo-container">
            <!-- Logo container in the middle -->
            <img class="logo" src="images/main/logo.jpg" alt="Logo" />
          </div>
          <ul class="right-links">
            <!-- Navigation links on the right side -->
            <li><a href="#section-3" on:click|preventDefault={scrollIntoView}>Contact</a></li>
            <li><a href="#section-2" on:click|preventDefault={scrollIntoView}>About</a></li>
          </ul>
        </nav>
      </nav>
    </div>
  </div>
</header>

<style>
  .clearfix:after {
    visibility: hidden;
    display: block;
    font-size: 0;
    content: " ";
    clear: both;
    height: 0;
  }

  * {
    -moz-box-sizing: border-box;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
  }

  .logo {
    max-width: 160px;
    margin-top: 30px;
    transition: all 0.5s ease;
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
    list-style: none;
    display: flex;
  }

  header nav ul li {
    margin: 0;
    text-align: center;
    transition: all 0.5s ease;
  }

  header nav ul li:hover {
    background: none;
    transform: scale(1.1);
    transition: transform 1s;
  }

  header nav ul li a {
    text-decoration: none;
    padding: 15px 20px;
    color: #000000;
    margin: 0;
    text-transform: uppercase;
    font-family: 'Quicksand', sans-serif;
    font-size: 1rem;
    transition: font-size 0.5s ease, padding 0.5s ease;
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

  @media screen and (max-width: 768px) {
    .logo {
      max-width: 120px;
      margin-top: 15px;
    }

    header nav ul li {
      padding: 10px 15px; /* Reduce padding */
    }

    header nav ul li a {
      font-size: 0.8rem; /* Reduce font size */
    }
  }
</style>
