<script>
  function scrollIntoView(target) {
    const sectionId = `section-${target}`;
    const el = document.getElementById(sectionId);
    el.scrollIntoView({
      behavior: 'smooth',
    });
  }
</script>


<header>
  <div class="navWrapper" id="home">
    <nav class="mainNav">
      <div class="left-links">
        <ul>
          <li><button on:click={() => window.location.href = '/'}>Home</button></li>
          <li><button on:click={() => window.location.href = '/gallery-index'}>Gallery</button></li>
        </ul>
      </div>
      <div class="logo-container">
        <img class="logo" src="images/main/logo.jpg" alt="Logo" />
      </div>
      <div class="right-links">
        <ul>
          <li><button on:click|preventDefault={() => scrollIntoView(2)}>About</button></li>
          <li><button on:click|preventDefault={() => scrollIntoView(3)}>Contact</button></li>
          
        </ul>
      </div>
    </header>

<style>
  header {
    background-color: rgb(255, 255, 255);
    margin-bottom: 20px;
    position: relative;
  }

  .mainNav {
    width: 100%; /* Make the navigation bar 100% of the screen width */
    background: rgb(255, 255, 255);
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .left-links ul,
  .right-links ul {
    list-style: none;
    display: flex;
    padding: 0;
    margin: 0;
  }

  .left-links li,
  .right-links li {
    text-align: center;
    padding: 10px 15px;
  }

  .left-links button,
  .right-links button {
    background: none;
    border: none;
    cursor: pointer;
    font-size: 1rem;
  }

  .logo {
    max-width: 160px;
    max-height: 60px;
  }

  @media (max-width: 768px) {
    .left-links li,
    .right-links li {
      font-size: 14px; /* Reduce font size for smaller screens */
    }

    .left-links button,
    .right-links button {
      font-size: 14px; /* Reduce font size for smaller screens */
    }

    .logo {
      max-width: 120px; /* Reduce logo size for smaller screens */
      max-height: 45px;
    }
  }
</style>
