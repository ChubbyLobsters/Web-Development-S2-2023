<script>
  import SvelteLayout from '../+layout.svelte';
  import Layout from '../../lib/galleryIndex.svelte';
 
  let myImages = [
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
  font-size: 50px;
}
</style>
