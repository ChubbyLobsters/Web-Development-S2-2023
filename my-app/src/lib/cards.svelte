<!-- Cards.svelte -->

<script>
    import { onMount } from 'svelte';

    let cards = [];
    let visibleCards = [];
    let currentPage = 1;
    const cardsPerRow = 3;
    const numRows = 2;
    const cardsPerPage = cardsPerRow * numRows;
    let selectedRarity = ''; // Store the selected rarity
    let searchQuery = ''; // Store the search query

    onMount(async () => {
        // Fetch data from the API
        const response = await fetch('https://api.magicthegathering.io/v1/cards?contains=imageUrl');
        const data = await response.json();

        // Extract cards from the data
        cards = data.cards;

        // Initialize the visible cards
        updateVisibleCards();
    });

    function updateVisibleCards() {
        const filteredCards = cards.filter(card => {
            const matchesRarity = !selectedRarity || card.rarity === selectedRarity;
            const matchesName = !searchQuery || card.name.toLowerCase().includes(searchQuery.toLowerCase());
            return matchesRarity && matchesName;
        });

        const startIndex = (currentPage - 1) * cardsPerPage;
        const endIndex = startIndex + cardsPerPage;
        visibleCards = filteredCards.slice(startIndex, endIndex);
    }

    function nextPage() {
        if (currentPage * cardsPerPage < visibleCards.length) {
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
        currentPage = 1; // Reset to the first page when changing search query
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
        <button class="button {currentPage === 1 ? 'disabled' : ''}" on:click={prevPage} disabled={currentPage === 1}>Previous Page</button>
        <button class="button {currentPage * cardsPerPage >= visibleCards.length ? 'disabled' : ''}" on:click={nextPage} disabled={currentPage * cardsPerPage >= visibleCards.length}>Next Page</button>
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
        font-family: Arial, sans-serif; /* font family */
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
</style>
