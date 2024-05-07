<script>
	import { onMount } from 'svelte';

	let cards = [];

	// Fetch JSON data
	async function fetchData() {
		const response = await fetch(
			'./src/lib/components/cards/title-content-hover-card/card-content.json'
		); // Adjust the path accordingly
		const data = await response.json();
		cards = data;
	}

	// Call the function to fetch data after the component is mounted
	onMount(fetchData);
</script>

<main>
	{#each cards as card}
		<div class="card">
			<img
				src="https://images.unsplash.com/photo-1656618020911-1c7a937175fd?crop=entropy&cs=tinysrgb&fm=jpg&ixid=MnwzMjM4NDZ8MHwxfHJhbmRvbXx8fHx8fHx8fDE2NTc1MzQyNTE&ixlib=rb-1.2.1&q=80"
				alt=""
			/>
			<div class="card-content">
				<h2>{card.heading}</h2>
				<p>{card.content}</p>
				<a href="javascript:void(0)" class="button">
					{card.button_text}
				</a>
			</div>
		</div>
	{/each}
</main>

<style lang="scss">
	// Colors
	$color-primary-white: rgb(240, 240, 240);

	.card {
		width: 24rem;
		height: 36rem;
		border-radius: 10px;
		overflow: hidden;
		cursor: pointer;
		position: relative;
		color: $color-primary-white;
		box-shadow: 0 10px 30px 5px rgba(0, 0, 0, 0.2);

		img {
			position: absolute;
			object-fit: cover;
			width: 100%;
			height: 100%;
			top: 0;
			left: 0;
			opacity: 0.9;
			transition: opacity 0.2s ease-out;
		}

		h2 {
			position: absolute;
			inset: auto auto 30px 30px;
			margin: 0;
			transition: inset 0.3s 0.3s ease-out;
			font-family: 'Roboto Condensed', sans-serif;
			font-weight: normal;
			text-transform: uppercase;
		}

		p,
		a {
			position: absolute;
			opacity: 0;
			max-width: 80%;
			transition: opacity 0.3s ease-out;
		}

		p {
			inset: auto auto 80px 30px;
		}

		a {
			inset: auto auto 40px 30px;
			color: inherit;
			text-decoration: none;
		}

		&:hover h2 {
			inset: auto auto 220px 30px;
			transition: inset 0.3s ease-out;
		}

		&:hover p,
		&:hover a {
			opacity: 1;
			transition: opacity 0.5s 0.1s ease-in;
		}

		&:hover img {
			transition: opacity 0.3s ease-in;
			opacity: 1;
		}
	}

	.material-symbols-outlined {
		vertical-align: middle;
	}
</style>
