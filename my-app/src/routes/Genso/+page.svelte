<script>
  import Layout from '../../lib/galleryIndex.svelte';
  import Footer from "../../lib/routeFooter.svelte";
  let myImages = [
  'images/genso/genso1.JPG',
  'images/genso/genso2.JPG',
  'images/genso/genso3.JPG',
  'images/genso/genso4.JPG',
  'images/genso/genso5.JPG',
  'images/genso/genso6.JPG',
  'images/genso/genso7.JPG',
  'images/genso/genso8.JPG',
  'images/genso/genso9.JPG',
  'images/genso/genso10.JPG',
  'images/genso/genso11.JPG',
  'images/genso/genso12.JPG',
  'images/genso/genso13.JPG',
  'images/genso/genso14.JPG',
];
import Loading from "../lib/loading.svelte";
    </script>

<Loading />
<div class="profile-container">
  <div class="center-profile">
    <h2 class="profile-title">Gensō-tekina Kaosu 幻 想 的 な カ オ ス  </h2>
    <h3 class="profile-blurb">
      Fantastical Chaos
    </h3>
  </div>
</div>


<Layout images={myImages} altText="Custom Alt Text" />

<Footer />

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
 