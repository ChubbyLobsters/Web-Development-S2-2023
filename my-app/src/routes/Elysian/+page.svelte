<script>
  import Layout from '../../lib/galleryIndex.svelte';

  let myImages = [
    'images/elysian/elysian5.jpg',
    'images/elysian/elysian3.png',
    'images/elysian/elysian9.jpg',
  ];
</script>

<div class="profile-container">
  <div class="center-profile">
    <h2 class="profile-title">Elysian Echoes: Chronicles of the Fallen Seraph </h2>
    <h3 class="profile-blurb">
      Lost Beyond The Sphare
    </h3>
  </div>
</div>


<div style="text-align: center;">
  <img src="images/elysian/elysian1.JPG" alt="Custom Alt Text" style="width: 100%; max-width: 85%; margin: 0 auto; padding-bottom: 14px;" />
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
 
 </style>