<script>
	import { Card } from 'flowbite-svelte';
	import { onMount } from 'svelte';

	let cards = [];

	// Fetch JSON data
	async function fetchData() {
		const response = await fetch('./src/lib/components/cards/./ProfileCards/ProfileInfo.json'); // Adjust the path accordingly
		const data = await response.json();
		cards = data;
	}

	// Call the function to fetch data after the component is mounted
	onMount(fetchData);
</script>

<link
	rel="stylesheet"
	href="https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css"
/>
{#each cards as card}
	<div class="container">
		<div class="card">
			<div class="content">
				<div class="img"><img src={card.ImageSrc} /></div>
				<div class="cardContent">
					<h3>{card.Name}<br /><span>{card.Position}</span></h3>
				</div>
			</div>
			<ul class="sci">
				<li style="--i:1">
					<a href={card.Facebook}><i class="fa fa-facebook" aria-hidden="true"></i></a>
				</li>
				<li style="--i:2">
					<a href={card.Instagram}><i class="fa fa-instagram" aria-hidden="true"></i></a>
				</li>
				<li style="--i:3">
					<a href={card.Github}><i class="fa fa-github" aria-hidden="true"></i></a>
				</li>
				<li style="--i:4">
					<a href={card.Linkedin}><i class="fa fa-linkedin" aria-hidden="true"></i></a>
				</li>
			</ul>
		</div>
	</div>
{/each}

<style lang="scss">
	$colors: (
		one: #990033,
		two: #161623,

		negro: #020202,
		blanco: #ffffff,
		sombra: #000000
	);

	@function color($color-name) {
		@return map-get($colors, $color-name);
	}

	@mixin displayFlex($justify, $align, $direction) {
		display: flex;
		justify-content: $justify;
		align-items: $align;
		flex-direction: $direction;
	}

	@keyframes colorful {
		0% {
			filter: hue-rotate(0deg);
		}
		100% {
			filter: hue-rotate(360deg);
		}
	}

	*,
	*::before,
	*::after {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
		text-decoration: none;
		list-style: none;
		outline: none;
		appearance: none;
		border-style: none;
		color: color(blanco);
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
	}

	h1,
	h2,
	h3,
	span,
	p {
		font-family:
			'Montserrat',
			-apple-system,
			BlinkMacSystemFont,
			'Segoe UI',
			'Roboto',
			'Oxygen',
			'Ubuntu',
			'Cantarell',
			'Fira Sans',
			'Droid Sans',
			'Helvetica Neue',
			sans-serif;
	}

	body {
		.container {
			position: relative;
			z-index: 1;
			@include displayFlex(center, center, row);
			flex-wrap: wrap;
			padding: 1em;

			.card {
				position: relative;
				width: 300px;
				height: 400px;
				margin: 1em;
				background: #302c2c;
				box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
				border-radius: 15px;
				@include displayFlex(center, center, column);
				backdrop-filter: blur(40px);

				border: solid 2px transparent;
				background-clip: padding-box;
				box-shadow: 0px 10px 10px rgba(46, 54, 68, 0.03);

				.content {
					position: relative;
					@include displayFlex(center, center, column);
					opacity: 0.5;
					transition: 0.5s;

					.img {
						position: relative;
						width: 150px;
						height: 150px;
						border-radius: 50%;
						overflow: hidden;
						border: 10px solid rgba(0, 0, 0, 0.25);

						img {
							position: absolute;
							top: 0;
							left: 0;
							width: 100%;
							height: 100%;
							object-fit: cover;
						}
					}

					.cardContent {
						h3 {
							color: #fff;
							text-transform: uppercase;
							letter-spacing: 2px;
							font-weight: 500;
							font-size: 18px;
							text-align: center;
							margin: 20px 0 10px;
							line-height: 1.1em;

							span {
								font-size: 12px;
								font-weight: 300;
								text-transform: initial;
							}
						}
					}
				}

				.sci {
					position: absolute;
					bottom: 50px;
					@include displayFlex(center, center, row);

					li {
						margin: 0 10px;
						transform: translateY(40px);
						opacity: 0;
						transition: 0.5s;
						transition-delay: calc(0.1s * var(--i));

						a {
							font-size: 24px;
						}
					}
				}

				&:hover .content {
					opacity: 1;
					transform: translateY(-20px);
				}

				&:hover .sci li {
					transform: translateY(0px);
					opacity: 1;
				}
			}
		}
	}
</style>
