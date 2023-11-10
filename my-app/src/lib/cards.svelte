<!-- Cards.svelte -->

<script>
  import { onMount } from 'svelte';
  import { afterUpdate } from 'svelte';
  let cards = [];
  let visibleCards = [];
  let currentPage = 1;
  const cardsPerRow = 3;
  const numRows = 2;
  const cardsPerPage = cardsPerRow * numRows;
  let selectedRarity = ''; // Store the selected rarity
  let searchQuery = ''; // Store the search query
  let isFiltering = false; // Track whether filtering is active
  function makeAjaxRequest(url, method, callback) {
      const xhr = new XMLHttpRequest();
      
      xhr.open(method, url, true);
      xhr.onload = function () {
          if (xhr.status >= 200 && xhr.status < 300) {
              const data = JSON.parse(xhr.responseText);
              callback(data);
          } else {
              console.error('AJAX request failed:', xhr.status, xhr.statusText);
          }
      };
      xhr.onerror = function () {
          console.error('AJAX request failed.');
      };
      xhr.send();
  }
  onMount(() => {
      // Make an AJAX request to fetch data from the API
      makeAjaxRequest('https://api.magicthegathering.io/v1/cards?contains=imageUrl', 'GET', (data) => {
          // Extract cards from the data
          cards = data.cards;
          
          // Initialize the visible cards
          updateVisibleCards();
      });
  });
  function updateVisibleCards() {
      const startIndex = (currentPage - 1) * cardsPerPage;
      const endIndex = startIndex + cardsPerPage;
      visibleCards = cards.slice(startIndex, endIndex);
  }
  function nextPage() {
      if (currentPage * cardsPerPage < cards.length) {
          currentPage++;
          updateVisibleCards();
      }
  }
  function prevPage() {
      if (currentPage > 1) {
          currentPage--;
          updateVisibleCards();
      }
  }
  function onRarityChange(event) {
      selectedRarity = event.target.value;
      currentPage = 1; // Reset to the first page when changing rarity
      updateVisibleCards();
  }
  function onSearchInputChange(event) {
      searchQuery = event.target.value;
      isFiltering = true; // Set filtering to true when the user types
  }
  // Use the afterUpdate lifecycle function to handle search filtering
  afterUpdate(() => {
      if (isFiltering) {
          currentPage = 1; // Reset to the first page when changing the search query
          updateVisibleCards();
          isFiltering = false; // Reset filtering state
      }
  });
  function search() {
      currentPage = 1; // Reset to the first page when performing a new search
      updateVisibleCards();
  }
</script>

<div class="container">
  <div class="grid">
      {#each visibleCards as card, index}
          <div class="card">
              <img src={card.imageUrl || 'placeholder_image_url'} alt={card.name || 'Card Name'} />
              <div class="info">
                  <h1>{card.name || 'Card Name'}</h1>
                  <p>{card.rarity || 'Card Rarity'}</p>
              </div>
          </div>
      {/each}
  </div>
  <div class="buttons">
    <button class="button {currentPage === 1 || cards.length === 0 ? 'disabled' : ''}" on:click={prevPage} disabled={currentPage === 1 || cards.length === 0}>Previous Page</button>
    <button class="button {currentPage * cardsPerPage >= cards.length ? 'disabled' : ''}" on:click={nextPage} disabled={currentPage * cardsPerPage >= cards.length}>Next Page</button>
  </div>
  <div class="filter">
      <label for="raritySelect">Select Rarity:</label>
      <select id="raritySelect" on:change={onRarityChange}>
          <option value="">All</option>
          <option value="Common">Common</option>
          <option value="Uncommon">Uncommon</option>
          <option value="Rare">Rare</option>
          <option value="Mythic">Mythic</option>
      </select>
      <input type="text" id="searchInput" placeholder="Search by Name" on:input={onSearchInputChange} />
      <button class="search-button" on:click={search}>Search</button>
  </div>
</div>

<style>
  .container {
      display: flex;
      flex-direction: column;
      align-items: center;
  }
  .grid {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
  }
  .card {
      width: calc(33.33% - 20px);
      margin: 10px;
      display: flex;
      flex-direction: column;
      align-items: center;
      font-family: Arial, sans-serif;
      transition: transform 0.3s ease-in-out; 
  }
  .card:hover {
      transform: scale(1.1); 
  }
  .card img {
      max-width: 100%; 
      height: auto; 
  }
  .buttons {
      display: flex;
      justify-content: center;
      margin: 10px;
  }
  .filter {
      display: flex;
      align-items: center;
      margin: 10px;
  }
  #raritySelect {
      margin-right: 10px;
  }
  .button {
      margin: 0 5px;
  }
  .info {
      text-align: center;
  }
  .search-button {
      margin-left: 10px;
  }
</style>