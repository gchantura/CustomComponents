<div class="container">
	<div class="cta">
		<img
			src="https://images.pexels.com/photos/705425/pexels-photo-705425.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260"
			alt=""
		/>
		<div class="text">
			<h2>The Title</h2>
			<p>
				Lorem ipsum dolor sit amet, consectetur adipisicing elit. Velit accusamus temporibus
				voluptates exercitationem, ipsa officiis a animi esse explicabo repudiandae in, blanditiis
				cum quam magni? Voluptates illum earum praesentium veniam.
			</p>
		</div>
	</div>
</div>

<style lang="scss">
	body {
		background: #111;
		font-family: 'Open Sans', sans-serif;
	}

	.cta-background {
		background-size: cover;
		background-position: center center;
		bottom: 0;
		filter: blur(50px);
		left: 0;
		position: absolute;
		right: 0;
		top: 0;
		width: 100%;
		z-index: -1;
	}

	.container {
		align-items: center;
		display: flex;
		height: 100vh;
		justify-content: center;
	}

	.cta {
		background: #333;
		box-shadow: 3px 3px 20px rgba(0, 0, 0, 0.2);
		height: 450px;
		overflow: hidden;
		position: relative;
		width: 300px;

		&:hover {
			img {
				top: -10%;
				filter: brightness(70%);
			}

			.text {
				bottom: 0;
			}
		}

		img {
			bottom: 0;
			filter: brightness(100%);
			left: 0;
			position: absolute;
			right: 0;
			top: 0;
			transition: 0.5s ease-in-out;
			width: 115%;
		}

		.text {
			bottom: -40%;
			padding: 15px;
			position: absolute;
			transition: 0.5s ease-in-out;

			h2 {
				color: #fff;
				display: inline-block;
				font-weight: 300;
				margin-bottom: 5px;
				position: relative;
			}

			p {
				color: #fff;
				font-weight: 300;
			}
		}
	}
</style>
