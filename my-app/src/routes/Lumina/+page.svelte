<script>
  import SvelteLayout from '../+layout.svelte';
  import Layout from '../../lib/galleryIndex.svelte';

  const myImages = [
    'images/lumina/Lumina1.jpeg',
    'images/lumina/Lumina2.jpeg',
    'images/lumina/Lumina3.jpeg',
    'images/lumina/Lumina4.jpeg',
    'images/lumina/Lumina5.jpeg',
  ];
</script>

<div class="profile-container">
  <div class="center-profile">
    <img src="images/lumina/profile1.png" alt="" class="profile-image" />
    <a href="https://www.instagram.com/stemkun/" class="profile-name">HAKI</a>
  </div>
</div>

<Layout images={myImages} altText="Custom Alt Text" />

<style>
  .profile-container {
    width: 100%;
    background-color: white;
    padding: 20px;
    display: flex;
    align-items: center;
    justify-content: center; /* Center horizontally */
    height: 20vh; /* Center vertically using viewport height */
  }

  .center-profile {
    display: flex;
    align-items: center;
    flex-wrap: wrap; /* Allow items to wrap to the next line when the screen size is reduced */
  }

  .profile-image {
    width: 240px;
    height: 180px;
    border-radius: 50%;
    margin-right: 20px;
  }

  .profile-name {
    cursor: pointer;
    color: black;
    font-size: '50px';
  }

  @media (max-width: 768px) {
    .profile-name {
      font-size: '30px'; /* Reduce font size for smaller screens */
    }

    .profile-image {
      width: 160px; /* Reduce image size for smaller screens */
      height: 120px;
      margin-right: 10px;
    }
  }

  @media (max-width: 425px) {
    .profile-name {
      font-size: 20px; /* Further reduce font size for smaller screens */
    }

    .profile-image {
      width: 120px; /* Further reduce image size for smaller screens */
      height: 90px;
      margin-right: 5px;
    }
  }
</style>
