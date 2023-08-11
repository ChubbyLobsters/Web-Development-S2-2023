<!-- Footer.svelte -->
<script>
  // JavaScript code can be added here if needed
</script>

<style>
    /* body */
  body {
    margin: 0;
    padding: 0;
    font-size: 16px;
  }
  /* copyright font */
  p {
    font-size: 12px;
    margin-top: 16px;
  }
  /* footer details */
  footer {
    background-color: #fffffff6;
    text-align: center;
    padding: 20px;
  }
  /* footer link details */
  .footer-links {
    margin-top: 15px;
  }
  /* footer aspects details */
  .footer-links a {
    color: #333;
    text-decoration: none;
    margin: 0 20px;
    border-bottom: 2px solid transparent;
    transition: border-bottom-color 0.2s ease, transform 0.2s ease, opacity 0.2s ease;
  }
  /* footer assests effects */
  .footer-links a:hover {
    border-bottom-color: #000000;
    transform: scale(1.1);
    opacity: 0.7;
  }
  /* logo details */
  .logo {
    max-width: 95px;
    transition: transform 0.4s ease;
  }
  /* logo hover effects */
  .logo:hover {
    transform: scale(1.1);
  }
</style>

<footer>  <!-- calls using 'i' class to Awesome Fonts using stylesheet -->
  <img class="logo" src="src/lib/logo.png" alt="Our Company Logo" />
  <div class="footer-links">
    <a href="/"><i class="fas fa-home logo"></i></a>
    <a href="/about"><i class="fas fa-info-circle logo"></i></a>
    <a href="/contact"><i class="fas fa-envelope logo"></i></a>
  </div>
  <p>&copy; 2023 Cameron Yeoman. All rights reserved.</p>
</footer>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">