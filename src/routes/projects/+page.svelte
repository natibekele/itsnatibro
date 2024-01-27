<script type="text/javascript">
	import { fade, scale, fly } from "svelte/transition";
	import AnimatedText from "$lib/AnimatedText.svelte"
	import RotatingSphere from "$lib/RotatingSphere.svelte"
	import WordSplit from "$lib/WordSplit.svelte"
	import LineSplit from "$lib/LineSplit.svelte"
	import { quintOut } from 'svelte/easing';
	import { onMount } from "svelte"
	import anime from "animejs"


	onMount(startAnimation)

	function startAnimation() {
		anime({
			targets: '.marquee-container__block',
			translateX: '-66.66666%',
			duration: 20000,
			loop: true,
			easing: 'linear',
			// delay: anime.stagger(100)
		})
	}
</script>

<div class="container"  in:fade={{duration: 500 }} out:fade={{duration: 500}}>
	<div class="marquee-container">
		<div class="marquee-container__block">
			<h1 class="marquee-container__text">projects/</h1>
			<h1 class="marquee-container__text">projects/</h1>
			<h1 class="marquee-container__text">projects/</h1>
		</div>
		<div class="marquee-container__block">
			<h1 class="marquee-container__text">proyectos/</h1>
			<h1 class="marquee-container__text">proyectos/</h1>
			<h1 class="marquee-container__text">proyectos/</h1>
		</div>
<!-- 		<div class="marquee-container__block">
			<h1 class="marquee-container__text">projeks /</h1>
			<h1 class="marquee-container__text">projeks /</h1>
			<h1 class="marquee-container__text">projeks /</h1>
		</div> -->
	</div>


	<div class="projects-container">
		<div class="project">
			<div class="text-wrapper">
				<h3 class="project__title">/NostalgiaBox</h3>
				<h3 class="project__title">/NostalgiaBox</h3>
				<h3 class="project__title">/NostalgiaBox</h3>

				<a target="blank" href="https://nostalgiabox.app" class="site-link">Live Link.</a>
			</div>
			<div class="block"></div>
		</div>
		<div class="project">
			<div class="text-wrapper">
				<h3 class="project__title">/Football--Village</h3>
				<h3 class="project__title">/Football--Village</h3>
				<h3 class="project__title">/Football--Village</h3>

				<a target="blank" href="https://just-football.vercel.app" class="site-link">Live Link.</a>
			</div>
			<div class="block"></div>
		</div>
		<div class="project">
			<div class="text-wrapper">
				<h3 class="project__title">/New Frontier</h3>
				<h3 class="project__title">/New Frontier</h3>
				<h3 class="project__title">/New Frontier</h3>

				<a target="blank" href="https://www.sundance.org/blogs/2022-sundance-film-festival-new-frontier-spans-biodigital-terrain-blends-online-in-person-in-real-time/" class="site-link">Sundance Blog Post.</a>
			</div>
			<div class="block"></div>
		</div>
	</div>
</div>

<style>
	h3 {
		font-size: 2.4rem;
		letter-spacing: -0.2rem;
		margin: 0;
		font-weight: 500;
	}
	p {
		font-size: 1.6rem;
	}

	.container {
		display: grid;
		grid-template-columns: repeat(10, 1fr);
		grid-auto-rows: minmax(20rem, auto);
		font-family: 'Manrope';
		opacity: 1;
		margin: 0 2rem;
	}

	.marquee-container {
		position: fixed;
		top: 6rem;
		z-index: 0;
		width: calc(100vw - 4rem);
		height: 100%;
		overflow: hidden;
	}

	.marquee-container__block {
		display: flex;
		min-width: 100%;
/*		transform: translateX(30%);*/
		flex: 0 0 auto;
/*		gap: 0.1rem;*/
		min-width: 100%;
		width: fit-content;
	}
	.marquee-container__text {
		font-size: 30rem;
		margin-bottom: 0rem;
		margin-top:0rem;
/*		min-width: 100%;*/
		width: auto;
	}

	.projects-container {
		grid-column: 6/11;
		z-index: 2;
	}
	.project {
		width: 100%;
		height: auto;
		aspect-ratio: 7/4;
		padding: 2rem;
		background: var(--base);
		border: solid var(--primary);
		border-width: 0 0 1px 1px;
		color: var(--black);
		position: relative;
		overflow: hidden;
		transition: ease 0.6s;
	}
	.project__title {
		font-size: 2rem;
		line-height: 1.5;
		font-weight: normal;
		z-index: 1;
	}

	.site-link {
		color: inherit;
		margin-top: 10rem;
		text-decoration: none;
		font-size: 1.8rem;
		line-height: 1.5;
		font-weight: normal;
		font-style: italic;
		z-index: 1;
	}

	.text-wrapper {
		position: absolute;
		z-index: 2;
		transition: ease 0.6s;
	}
	.block {
		height: 100%;
		width: 100%;
		position: absolute;
		top: 0;
		left: 100%;
		background: var(--primary);
		z-index: 0;
		transition: ease 0.6s;
	}

	.project:hover {
		color: var(--white);
	}

	.project:hover > .block {
		transform: translateX(-100%);
	}



	@media(max-width: 800px) {
		.container {
			display: flex;
			flex-direction: column;
		}
		.block {
			flex-direction: column;
		}
		.child {
		}
	}
</style>