<script type="text/javascript">
	import IntersectionObserver from 'svelte-intersection-observer';
	import { onMount } from 'svelte';
	import WordSplit from './WordSplit.svelte';
	import anime from 'animejs';
	onMount(startAnimation);

	function startAnimation() {
		anime({
			targets: '.block_1',
			translateX: '-250%',
			duration: 35000,
			loop: true,
			easing: 'linear'
			// delay: anime.stagger(100)
		});
		anime({
			targets: '.block_2',
			translateX: '-250%',
			duration: 50000,
			loop: true,
			easing: 'linear',
			delay: anime.stagger(100)
		});
	}
	let node;
</script>

<div class="container">
	<h4 class="title marquee-container__text">meɪkə</h4>
	<WordSplit
		text={`
      One of the strangest things is the act of creation. You are faced with a blank slate—a page, a
		canvas, a block of stone or wood, a silent musical instrument. You then look inside yourself.
		You pull and tug and squeeze and fish around for slippery raw shapeless things that swim like
		fish made of cloud vapor and fill you with living clamor. You latch onto something. And you
		bring it forth out of your head like Zeus giving birth to Athena. And as it comes out, it takes
		shape and tangible form.It drips on the canvas, and slides through your pen, it springs forth
		and resonates into the musical strings, and slips along the edge of the sculptor’s tool onto the
		surface of the wood or marble.You have given it cohesion. You have brought forth something
		ordered and beautiful out of nothing.You have glimpsed the divine.`}
		initialDelay={6000}
	/>

	<div class="separator"></div>

	<h4 class="title marquee-container__text">wrk exprnce</h4>

	<div>
		<IntersectionObserver once element={node} let:intersecting>
			<div bind:this={node}>
				{#if intersecting}
					<WordSplit text={'full stack & founder / aberash / 2020- present'} initialDelay={0} />
					<WordSplit text={'front end dev / active theory / 2020- 2023'} initialDelay={250} />
					<WordSplit text={'freelance dev / 2019 - 2020'} initialDelay={500} />
					<WordSplit text={'software dev / wycliffe associates / 2018 - 2019'} initialDelay={750} />
				{/if}
			</div>
			<!-- <p class="para sm">full stack & founder / aberash / 2020- present</p>
		<p class="para sm">front end dev / active theory / 2020- 2023</p>
		<p class="para sm">freelance dev / 2019 - 2020</p>
		<p class="para sm">software dev / wycliffe associates / 2018 - 2019</p> -->
		</IntersectionObserver>
	</div>
</div>

<style>
	.container {
		grid-column: 7/10;
		grid-row: 1;
	}

	.separator {
		margin-top: 6rem;
		height: 1px;
		width: 100%;
		background: var(--primary);
	}

	.title {
		font-size: 8rem;
		letter-spacing: -1.44px;
		line-height: 110%;
		font-weight: 600;
		margin: 3.5rem 0;
	}

	.para {
		font-size: 1.6rem;
		letter-spacing: -0.32px;
		font-weight: 400;
		line-height: 1.5;
		margin: 0;
	}

	.sm {
		line-height: 140%;
	}

	@media (min-width: 1440px) {
		.title {
			font-size: 10rem;
		}
	}
	.marquee-container {
		position: relative;
		z-index: 0;
		width: 100%;
		overflow: hidden;
	}

	.marquee-container__block {
		display: flex;
		min-width: 100%;
		flex: 0 0 auto;
		gap: 50%;
		min-width: 100%;
		width: fit-content;
	}
	.marquee-container__text {
		/*margin-bottom: 0rem;*/
		/* margin-top: 0rem; */
		/*		min-width: 100%;*/
		width: auto;
	}
</style>
