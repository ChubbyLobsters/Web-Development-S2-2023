<script>
    // Define the routes for the buttons
    let route1 = "/route1";
    let route2 = "/route2";
  
    // Define the image sources for the buttons
    let imageSrc1 = "button1.jpg";
    let imageSrc2 = "button2.jpg"; 
  </script>
  
  <main>
    <div class="button-section">
      <a href={route1}>
        <img src={imageSrc1} alt="Button 1" />
      </a>
      <a href={route2}>
        <img src={imageSrc2} alt="Button 2" />
      </a>
    </div>
  </main>
  
  <style>
    main {
      text-align: center;
    }
  
    .button-section {
      display: flex;
      justify-content: center;
    }
  
    a {
      margin: 10px;
      text-decoration: none;
      color: inherit;
      display: inline-block;
    }
  </style>
  