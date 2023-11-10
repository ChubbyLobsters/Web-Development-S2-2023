<script>
  import Layout from '../../lib/galleryIndex.svelte';

  const myImages = [
    'images/bld/BLD1.png',
    'images/bld/BLD12.png',
    'images/bld/BLD2.png',
    'images/bld/BLD3.png',
    'images/bld/BLD4.png',
    'images/bld/BLD5.png',
  ];
</script>

<div class="profile-container">
  <div class="center-profile">
    <h2 class="profile-title">BLOOD LUST DEATH</h2>
    <p class="profile-blurb">
      A testament to the solitary realm,
      Where pristine artistry blooms, a symphony overwhelm.
      In mere hours ten, immaculate visions arise,
      A dance of flow, a mastery unveiled, to our wonder and surprise.
      These volumes, a ballet of crafted finesse,
      Unveiling the depths where artistry finds solace and caress.
      Thoughts take flight, creativity's breath alight,
      A chronicle of passion's journey, basking in the artist's resplendent light.
      Let these works transport you to realms untold,
      Where inspiration and dedication, a tale behold.
      With grace and eloquence, their stories unfurled,
      A testament to the artist's spirit, a gift to the world.
    </p>
  </div>
</div>
<Layout images={myImages} altText="Custom Alt Text" />

<style>
 .profile-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 40vh; /* Adjust the height as needed for your layout */
}

.center-profile {
  text-align: center;
  padding: 15px; /* Add space above and below the text */
  font-family: Arial, sans-serif; /* font family */
  width: 85%; 
}

.profile-title {
  font-size: 36px; 
  font-weight: bold; /* title bold */
}

.profile-blurb {
  font-size: 18px;
  line-height: 1.5; /* Increased line height for readability */
}

@media (max-width: 768px) {
  .profile-title {
    font-size: 24px; /* Reduce font size for smaller screens */
  }

  .profile-blurb {
    font-size: 16px; /* Reduce font size for smaller screens */
  }
}

@media (max-width: 768px) {
  .profile-title {
    font-size: 24px; 
  }

  .profile-blurb {
    font-size: 13px; 
  }
}

@media (max-width: 425px) {
  .profile-title {
    font-size: 20px; 
  }

  .profile-blurb {
    font-size:9px; 
  }
}
</style>
