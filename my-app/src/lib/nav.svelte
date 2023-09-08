<script>
</script>

<header>
  <div class="navWrapper" id="home">
    <div class="clearfix">
      <!-- Move the header content to the left -->
      <div class="headerLeft">
        <div class="companyName no-margin">Forgotten Dreams
          <div class="yearText">coming 2025</div>
        </div>
      </div>

      <nav class="mainNav clearfix">
        <nav>
          <ul>
            <li><a href="/">Home</a></li>
            <li><a href="/gallery">Gallery</a></li>
            <li><a href="/about">About</a></li>
            <li><a href="/contact">Contact</a></li>
          </ul>
        </nav>
        <div class="logo-container">
          <img class="logo" src="images/logo.png" alt="Logo" />
        </div>
      </nav>
    </div>
  </div>
</header>

<style>
  .clearfix:after {visibility: hidden; display: block; font-size: 0; content: " "; clear: both; height: 0; }

  * { -moz-box-sizing: border-box; -webkit-box-sizing: border-box; box-sizing: border-box; }

  .yearText {
    font-size: 0.6rem;
    font-family: 'Josefin Sans', sans-serif;
    color: #fff;
  }

  .companyName {
    padding: 21px 17px 10px 1.5%;
    float: left;
    color: #fff;
    width: 30%;
    background: rgba(0,0,0,0.7);
    font-family: 'Josefin Sans', sans-serif;
    font-weight: 400;
    font-size: 1.8rem;
    text-align: left;
    font-variant: small-caps;
  }

  nav {
    padding: 0;
    margin: 0;
    width: 55%;
    float: right;
  }

  header nav ul {
    float: right;
    display: inline-block;
    padding: 0;
    margin: 0;
    width: 100%;
    border-right: 20px solid rgba(0,0,0,0.7);
  }

  header nav ul li {
    float: left;
    margin: 0;
    display: inline;
    width: 25%;
    text-align: center;
    background: rgba(0,0,0,0.7);
  }

  header nav ul li:hover {
    background: none;
    transform: scale(1.2);
  }

  header nav ul li a {
    text-decoration: none;
    padding: 30px 20px;
    color: #fff;
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
    background-color: rgba(0, 0, 0, 7);
  }

  .logo-container {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    padding-right: 300px;
  }

  .logo {
    max-width: 230px;
    padding-top: 3.5px;
  }

</style>
