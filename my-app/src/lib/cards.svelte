<!-- Cards.svelte -->
<script>
  import { onMount, afterUpdate } from 'svelte';

  let cards = [];
  let visibleCards = [];
  let currentPage = 1;
  const cardsPerRow = 3;
  const numRows = 2;
  const cardsPerPage = cardsPerRow * numRows;
  let selectedRarity = '';
  let searchQuery = '';
  let isFiltering = false;

  async function makeFetchRequest(url) {
    try {
      const response = await fetch(url);
      if (response.ok) {
        const data = await response.json();
        return data.cards;
      } else {
        console.error('Fetch request failed:', response.status, response.statusText);
        return [];
      }
    } catch (error) {
      console.error('Fetch request failed:', error);
      return [];
    }
  }

  onMount(async () => {
    try {
      const data = await makeFetchRequest('https://api.magicthegathering.io/v1/cards?contains=imageUrl');
      cards = data;
      updateVisibleCards();
    } catch (error) {
      console.error('Error in onMount:', error);
    }
  });

  function updateVisibleCards() {
    const startIndex = (currentPage - 1) * cardsPerPage;
    const endIndex = startIndex + cardsPerPage;
    visibleCards = cards.slice(startIndex, endIndex);
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