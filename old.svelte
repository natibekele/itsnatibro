<script type="module">
	import {onMount} from "svelte"
	import { fade, scale } from "svelte/transition";
	import WorkExperience from "$lib/workExperience.svelte"
	import anime from "animejs"

	// onMount(_ => {
	// 	anime({
	// 		targets: '.block1',
	// 		keyframes: [
	// 			{translateY: '100%'},
	// 			{translateY: '0%'}
	// 		],
	// 		duration: 1000,
	// 		delay: 4000
	// 	})
	// })

	function onAppear() {
		console.log('onappear')
		anime({
			targets: '.block1',
			translateY: '0%',
			// keyframes: [
			// 	{translateY: '100%'},
			// 	{translateY: '0%'}
			// ],
			duration: 1000,
			delay: 4000
		})
	}

</script>
<div class="mgrid">

	<div class="block1"style="background: var(--light-blue);" 
	transition:fade|global
	on:introstart={() => (console.log('intro started'))}>
		<div class="window">
			<div class="dup">
				<img class="window__image" src="/images/sky.jpeg"/>
				<img class="window__image" src="/images/sky.jpeg"/>
				<img class="window__image" src="/images/sky.jpeg"/>
			</div>
		</div>
		<!-- <img src="https://images.unsplash.com/photo-1700684677600-e41b44847d18?q=80&w=2970&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="testing" /> -->
		<img src="https://images.unsplash.com/photo-1622396480801-a99a919f2e65?q=80&w=3087&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="testing" />
		<div class="text-block">
			<p> head in the clouds </p>
			<p> head in the clouds </p>
			<p> head in the clouds </p>
			<p> head in the clouds </p>
			<p> head in the clouds </p>
			<p> head in the clouds </p>
			<p> head in the clouds </p>
			<p> head in the clouds </p>
		</div>
	</div>
	<div class="block2">
		<h4 class="title">wrk exprnce</h4>

		<div>
			<p class="xp">full stack &  founder / aberash / 2020- present</p>
			<p class="xp">front end  dev / active theory / 2020- 2023</p>
			<p class="xp">freelance dev  / 2019 - 2020</p>
			<p class="xp">software dev / wycliffe associates / 2018 - 2019</p>
		</div>
	</div>

	<div class="block3"style="background: white;"></div>
	<div class="block4"style="background: var(--light-blue);">
		<img class="block4__image" src="images/house.jpeg"/>
	</div>
</div>


<style>
	.mgrid {
		display: grid;
		grid-template-columns: repeat(10, 1fr);
		grid-auto-rows: minmax(72rem, 90vh);
		font-family: 'Manrope';
	}

	.block1 {
		grid-column: 1/6;
		grid-row: 1;
		display: grid;
		grid-template-columns: repeat(10, 1fr);
		grid-auto-rows: auto;
/*		transform: translateY(100%);*/
	}
	.block1 > img {
		height: 100%;
		width: 100%;
		object-fit: cover;
		grid-column: 1/11;
		grid-row: 1;
	}

	.text-block {
		margin: auto;
		padding: 1.5rem 1.5rem;
/*		transform: rotateZ(90deg);*/
		background: var(--dynamic-orange);
/*		width: fit-content;*/
		grid-column: 2/4;
		grid-row: 1;
		display: flex;
		flex-direction: column;
		justify-content: space-evenly;
/*		display: none;*/
	}
	.text-block > p {
		font-size: 1.6rem;
		font-weight: 500;
		letter-spacing: -1px;
		width: fit-content;
	}

	.block2 {
		padding: 4.5rem 6rem;
		grid-column: 6/11;
		grid-row: 1;
		background: var(--black);
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}

	.block3 {
		grid-column: 1/6;
		grid-row: 2;
	}

	.block4 {
		grid-column: 6/11;
		grid-row: 2;
	}

	.block4__image {
		height: 100%;
		width: 100%;
		object-fit: cover;
	}

	.title {
		color: var(--white);
		font-size: 2rem;
		font-weight: 600;
		line-height: 110%;
		letter-spacing: -1.08px;
		margin: 0;
	}
	.xp {
		color: var(--white);
		font-size: 1.6rem;
		font-weight: 300;
		line-height: 120%;
	}

	.window {
		width: 14.25rem;
		height: 21rem;
		border-radius: 6rem;
		overflow: hidden;
		mix-blend-mode: hard-light;
		grid-column: 2;
		margin-top: 5rem;
		grid-row: 1;
	}

	.window__image {
		height: 100%;
		width: 150%;
	}
	.window__image:nth-child(2) {
		transform: rotateY(180deg);
	}

	.dup {
		display: flex;
		animation: fly 15s linear infinite;
	}

	@keyframes fly {
		0% {
			transform: translateX(0%);
		}


		100%{
			transform: translateX(-300%);
		}
	}

	@media(max-width: 768px) {
		.mgrid {
			grid-template-columns: 1z;
		}
	}
</style>