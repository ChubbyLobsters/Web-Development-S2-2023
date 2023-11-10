<!-- footer.svelte -->
<script>
  const scrollIntoView = (target) => {
    const el = document.querySelector(target);
    el.scrollIntoView({
      behavior: 'smooth'
    });
  };
</script>

<footer>
  <img class="logo" src="images/main/logo.jpg" alt="Logo" />

  <div class="footer-links">
    <a href="/" on:click|preventDefault={() => scrollIntoView("#home")}><i class="fas fa-home logo"></i></a>
    <a href="/about" on:click|preventDefault={() => scrollIntoView("#section-2")}><i class="fas fa-info-circle logo"></i></a>
    <a href="/contact" on:click|preventDefault={() => scrollIntoView("#section-3")}><i class="fas fa-envelope logo"></i></a>
  </div>

  <p>&copy; 2023 Forgotten Dreams. All rights reserved.</p>
</footer>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">

<style>
  p {
    font-size: 12px;
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
    display: flex;
    justify-content: center;
  }

  .footer-links a {
    color: #000000;
    text-decoration: none;
    margin: 0 10px; /* Reduced margin */
    font-size: 12px; /* Reduced font size */
    transition: border-bottom-color 0.2s ease, transform 0.2s ease, opacity 0.2s ease;
  }

  .footer-links a:hover {
    border-bottom-color: #808080;
    transform: scale(1.1);
    opacity: 0.7;
  }

  .logo {
    max-width: 70px;
    transition: transform 0.4s ease;
  }

  .logo:hover {
    transform: scale(1.1);
  }

  @media (max-width: 768px) {
    /* Adjustments for smaller screens */
    footer {
      padding: 10px; /* Reduce the padding */
    }

    .footer-links a {
      font-size: 14px; /* Reduce the font size */
    }

    .logo {
      width: 60px; /* Reduce the logo size */
    }
    
    p {

      font-size: 10px;
    }
  }


  @media (max-width: 600px) {
    /* Adjustments for smaller screens */
    footer {
      padding-top: 60px; /* Reduce the padding */
    }

    .footer-links a {
      font-size: 10px; /* Reduce the font size */
    }

    .logo {
      width: 55px; /* Reduce the logo size */
    }
  }
</style>
