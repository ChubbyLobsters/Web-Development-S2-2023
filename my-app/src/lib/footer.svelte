<!-- Footer.svelte -->
<script>
</script>

<footer> 
  <img class="logo" src="src/lib/logo.png" alt="Our Company Logo" />
  <div class="footer-links">
    <a href="/"><i class="fas fa-home logo"></i></a>
    <a href="/about"><i class="fas fa-info-circle logo"></i></a>
    <a href="/contact"><i class="fas fa-envelope logo"></i></a>
  </div>
  <p>&copy; 2023 Forgotten Dreams. All rights reserved.</p>
</footer>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">

<style>

  body {
    margin: 0;
    padding: 0;
    font-size: 16px;
  }

  p {
    font-size: 14px;
    margin-top: 16px;
    color: #d6d6d6;
  }
 
  footer {
    background-color: rgba(0,0,0,0.7);
    text-align: center;
    padding: 20px;
  }

  .footer-links {
    margin-top: 15px;
  }
 
  .footer-links a {
    color: #fffefe;
    text-decoration: none;
    margin: 0 20px;
    border-bottom: 2px solid transparent;
    transition: border-bottom-color 0.2s ease, transform 0.2s ease, opacity 0.2s ease;
  }

  .footer-links a:hover {
    border-bottom-color: #d6d6d6;
    transform: scale(1.1);
    opacity: 0.7;
  }

  .logo {
    max-width: 105px;
    transition: transform 0.4s ease;
  }

  .logo:hover {
    transform: scale(1.1);
  }
</style>
