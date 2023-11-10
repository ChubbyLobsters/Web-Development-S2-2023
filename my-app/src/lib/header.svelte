<!-- Header.svelte -->

<script>
</script>

<header class="header">
  <img src="images/main/header.jpg" alt="Header Image" />
</header>

<style>
  .header {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: #000000;
    border-radius: 20px;
  }

  .header img {
    max-width: 70%;
    max-height: 80%;
  }

  @media screen and (max-width: 768px) {
    .header {
      max-width: 90%;
      padding-left: 4.5%;
    }
  }

  @media screen and (max-width: 640px) {
    .header {
      height: 90%; /* Further height adjustment */
    }
  }

  @media screen and (max-width: 480px) {
    .header {
      height: 90%;
    }
  }
</style>
