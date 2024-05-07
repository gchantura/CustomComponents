<script>
	import Card0004 from '../lib/components/cards/Card0004/Card0004.svelte';
	import Titlecontenthover from '../lib/components/cards/HoverRightToLeftCard/titlecontenthover.svelte';
	import ImageHoverTextCard from '../lib/components/cards/IMageHoverTextCard/ImageHoverTextCard.svelte';
	import ProfileCards from '../lib/components/cards/ProfileCards/ProfileCards.svelte';
	import TitledContentReadMoreHover from '../lib/components/cards/title-content-hover-card/TitledContentReadMoreHover.svelte';
</script>

<div class="container flex bg-gray-600">
	<section class="cards">
		<div class="cardSection">
			<Titlecontenthover />
		</div>
		<div class="cardSection">
			<TitledContentReadMoreHover />
		</div>
		<div class="cardSection">
			<ImageHoverTextCard />
		</div>
		<div class="cardSection">
			<Card0004 />
		</div>
	</section>
</div>
<ProfileCards />

<style>
	* {
		padding: 0%;
		margin: 0%;
		box-sizing: border-box;
	}
	.container {
		display: flex;
		justify-content: center;
		align-items: center;
		height: 100vh;
		background-color: gray;
	}

	.cards {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
	}
</style>
