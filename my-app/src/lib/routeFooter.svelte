<!-- Footer.svelte -->
<script>
  function scrollIntoView(target) {
    const el = document.querySelector(target);
    el.scrollIntoView({
      behavior: 'smooth'
    });
  }
</script>

<footer>
  <img class="logo" src="images/main/logo.jpg" alt="Logo" />
  <div class="footer-links">
    <a href="/" on:click|preventDefault={() => scrollIntoView("#home")}><i class="fas fa-home logo"></i></a>
  </div>
  <p>&copy; 2023 Forgotten Dreams. All rights reserved.</p>
</footer>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">

<style>

  p {
    font-size: 14px;
    margin-top: 16px;
    color: #000000;
  }
 
  footer {
    background-color: rgba(255, 255, 255, 0.897);
    text-align: center;
    padding: 20px;
  }

  .footer-links {
    margin-top: 15px;
  }
 
  .footer-links a {
    color: #000000;
    text-decoration: none;
    margin: 0 20px;
    border-bottom: 2px solid transparent;
    transition: border-bottom-color 0.2s ease, transform 0.2s ease, opacity 0.2s ease;
  }

  .footer-links a:hover {
    border-bottom-color: #808080;
    transform: scale(1.1);
    opacity: 0.7;
  }

  .logo {
    max-width: 105px;
    transition: transform 0.4s ease;
    position: center;
  }

  .logo:hover {
    transform: scale(1.1);
  }
</style>
