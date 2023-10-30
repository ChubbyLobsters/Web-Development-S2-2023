<script>
	import { onMount, afterUpdate } from 'svelte'; 	
	let active = false;
	let cards = [];
	let currentPage = 1;
	let cardsPerPage = 8; // 8 cards per page
	let randomCard;
	let visibleCards = [];

	onMount(async () => {
		// Fetch data from the API
		const response = await fetch('https://api.magicthegathering.io/v1/cards?contains=imageUrl');
		const data = await response.json();

		// Extract cards from the data
		cards = data.cards;
		updateVisibleCards();
	});

	afterUpdate(() => {
		updateVisibleCards();
	});

	function updateVisibleCards() {
		const startIndex = (currentPage - 1) * cardsPerPage;
		const endIndex = startIndex + cardsPerPage;
		visibleCards = cards.slice(startIndex, endIndex);
	}

	function getRandomCard() {
		active = !active;
		// Generate a random index to pick a random card
		const randomIndex = Math.floor(Math.random() * cards.length);
		randomCard = cards[randomIndex];
	}

	function nextPage() {
		currentPage += 1;
	}

	function prevPage() {
		if (currentPage > 1) {
			currentPage -= 1;
		}
	}
</script>

  <!-- grid and buttons sections -->
  

  <div class="grid">
	{#each visibleCards as card}
		<div class="card">
			<img src={card.imageUrl || 'placeholder_image_url'} alt={card.name || 'Card Name'} />
			<div class="info">
				<h1>{card.name || 'Card Name'}</h1>
				<p>{card.text || 'Card Description'}</p>
			</div>
		</div>
	{/each}
</div>


{#if active}
<img src={randomCard.imageUrl} class="randomCard"  />
{/if}

<div class="buttons">
	<button class="button {currentPage === 1 ? 'disabled' : ''}" on:click={prevPage} disabled={currentPage === 1}>Previous Page</button>
	<button class="button {currentPage * cardsPerPage >= cards.length ? 'disabled' : ''}" on:click={nextPage} disabled={currentPage * cardsPerPage >= cards.length}>Next Page</button>
	<div class="button randomize" on:click={getRandomCard}>Show Random Card</div>
</div>




<style>
	.grid {
	  display: grid;
	  grid-template-columns: repeat(4, 1fr);
	  gap: 20px;
	  text-align: center;
	}
  
	.card {
	  display: flex;
	  flex-direction: column; /* Change to column layout */
	  align-items: center; /* Center content vertically */
	  padding: 0;
	  position: relative;
	}
  
	.card img {
	  max-width: 100%;
	  max-height: 100px;
	  object-fit: cover;
	  transition: transform 0.3s;
	}
  
	.card img:hover {
	  transform: scale(1.2);
	}
  
	.info {
	  font-size: 8px;
	  margin-top: 5px;
	}
  
	.buttons {
	  display: flex;
	  justify-content: center;
	  gap: 20px;
	  margin-top: 80px;
	  margin-bottom: 80px;
	}
  
	.button {
	  background-color: black;
	  color: white;
	  border: none;
	  border-radius: 5px;
	  padding: 10px 20px;
	  cursor: pointer;
	  transition: opacity 0.3s;
	}
  

  
	.button.disabled {
	  opacity: 0.3;
	  pointer-events: none;
	}

	.randomCard {
	position:fixed ;
	justify-content: center;
	}
  </style>