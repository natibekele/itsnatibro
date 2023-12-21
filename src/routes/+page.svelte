<script type="module">
	import {onMount} from "svelte"
	import { fade, scale, fly } from "svelte/transition";
	import WorkExperience from "$lib/workExperience.svelte"
	import MakerBlock from "$lib/makerBlock.svelte"
	import TechBlock from "$lib/techBlock.svelte"
	import LittleScene from "$lib/LittleScene.svelte"
	import HorizontalScroll from "$lib/horizontalScroll.svelte"
	import Cover from "$lib/Cover.svelte"
	import anime from "animejs"
	import { Canvas } from "@threlte/core"
	import { HTML } from "@threlte/extras"

	import Rellax from "rellax"
	let observer;
	let translation = 0;
	let horizontal;
	let mounted = false;
	let coverDelay = 6000;
	let defaultDuration = 700;
	onMount(() => {
		setTimeout(_ => {
			introTimeline()
			onAppear();
		}, coverDelay);
		mounted = true;
	});

	function introTimeline() {
		var timeline = anime.timeline({
			easing: 'easeOutExpo',
			duration: 400
		})

		if (document.querySelector('.mgrid').clientWidth < 800) return;
		var rellax = new Rellax('.g1');
		var rx = new Rellax('.g3');
		var rx2 = new Rellax('.g4')

	}

	function onAppear() {
		anime({
			targets: '.slash',
			opacity: [
				{ value: 1, duration: 1000, delay: 10000 },
				{ value: 0, duration: 1000, delay: 0 },
				{ value: 1, duration: 1000, delay: 0 },
				{ value: 0, duration: 1000, delay: 0 },
				{ value: 1, duration: 1000, delay: 0 },
				{ value: 0, duration: 1000, delay: 0 },
				],
			easing: 'easeInOutSine',
			loop: true
		})
	}

	const defInTransition = { delay: coverDelay, duration: defaultDuration }
	const defOutTransition = { delay: defaultDuration + 100, duration: defaultDuration }

</script>

{#if mounted}
<div class="mgrid" 
		in:fly={{...defInTransition, x: '0%'}}
		out:fly={{...defInTransition, x: '100%'}}>

	<div class="block1" 
		on:introstart={() => (console.log('intro started'))}
	>
		<img src="/images/sky.jpeg" alt="sky and clouds" />
	</div>

	<MakerBlock /> 
	
	<img class="slash" src="images/slash.svg" alt="rhyme" />

	<TechBlock />

	<div class="grid-image g1">
		<img src="http://tinyurl.com/ms465e32" alt="laptop"/>
	</div>

	<div class="grid-image g2" data-rellax-speed="1">
		<img src="http://tinyurl.com/477ev6n6" alt="record player"/>
	</div>

	<div class="grid-image g3">
		<img src="http://tinyurl.com/4y6y96x4" alt="editorial"/>
	</div>
	<div class="grid-image g4">
		<img src="http://tinyurl.com/mv6vt26f" alt="flowers"/>
	</div>
	<div class="grid-image g5">
		<img src="http://tinyurl.com/ye2jx9uy" alt="arduino"/>
	</div>
	<div class="grid-image g6" >
		<img src="http://tinyurl.com/av7m3ra9" alt="plants"/>
	</div>
	<div class="video-block">
		<video type="video/mp4" src="/videos/comp.mp4" muted=true autoplay=true loop/>
		<div class="overlay"></div>
	</div>

</div>

{/if}

<Cover />


<style>
	.mgrid {
		display: grid;
		grid-template-columns: repeat(10, 1fr);
		grid-auto-rows: minmax(20rem, auto);
		font-family: 'Manrope';
		margin: 0 2rem;
		opacity: 1;
	}

	.slash {
		position: absolute;
		top: 60%;
		left: 50%;
		transform: translate(-50%, -50%);
		mix-blend-mode: color-burn;
		opacity: 0;
	}

	.block1 {
		margin-top: 3.5rem;
		grid-column: 1/6;
		grid-row: 1;
		border-radius: 20rem;
		overflow: hidden;
		max-height: 86.6rem;
		margin-bottom: 10rem;
	}
	.block1 > img {
		height: 100%;
		width: 100%;
		object-fit: cover;
		grid-column: 1/11;
		grid-row: 1;
	}

	.threeD {
		grid-column: 1/11;
		height: 100vh;
		margin-bottom: 10rem;
	}

	.video-block {
		margin-bottom: 13.5rem;
		grid-column: 2/10;
		grid-row: 9;
		max-height: 75rem;
		overflow: hidden;
		border-radius: 20rem;
		aspect-ratio: 1200 / 750;
		position: relative;

	}
	.video-block > video {
		height: 100%;
		width: 100%;
		object-fit: cover;
	}

	.overlay {
		height: 100%;
		width: 100%;
		position: absolute;
		top: 0;
		left: 0;
		background: var(--primary);
		opacity: 0.2;
		z-index: 9;
	}

	.grid-image {
		/*height: 20rem;
		width: 20rem;*/
	}
	.grid-image > img {
		height: 100%;
		width: 100%;
		object-fit: contain;
	}
	.g1 {
		grid-row:3;
		grid-column: 2/5;
		z-index: 1;
	}
	.g2 {
		grid-column: 6/9;
	}
	.g3 {
		grid-column: 4/5;
		grid-row: 5;
	}
	.g4 {
		grid-column: 8/11;
		grid-row: 6;
	}
	.g5 {
		grid-column: 5/7;
		grid-row: 7;
	}
	.g6 {
		grid-column: 1/4;
		grid-row: 8;
		margin-bottom: 15rem;
	}

	@keyframes fly {
		0% {
			transform: translateX(0%);
		}


		100%{
			transform: translateX(-300%);
		}
	}
	@media(max-width: 800px) {
		.mgrid {
			display: flex;
			flex-direction: column;
		}
		.block1 {
			grid-row: auto;
		}
		.container {
			grid-row: auto;
		}
		.slash {
			top: 50%;
		}
	}
	@media(max-width: 768px) {
		.mgrid {
			grid-template-columns: 1fr;
		}
	}
</style>