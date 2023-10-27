<script>
    // Define an array of words
    let words = ["Word1", "Word2", "Word3", "Word4", "Word5"];
  
    // Function to handle hover
    function handleHover(event) {
      event.target.style.color = "gray";
    }
  
    // Function to handle mouseout
    function handleMouseOut(event) {
      event.target.style.color = "black";
    }
  </script>
  
  <div>
    <h1>Welcome to the Index Page</h1>
    <ul>
      {#each words as word (word)}
        <li on:mouseenter={handleHover} on:mouseleave={handleMouseOut}>
          <span class="word">{word}</span>
        </li>
      {/each}
    </ul>
  </div>

  <style>
    /* Add styles to the words */
    .word {
      transition: color 0.3s; /* Smooth color transition */
    }
  </style>
  
  