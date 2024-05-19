<script>
	import IntersectionObserver from 'svelte-intersection-observer';
	import { fade } from 'svelte/transition';
	import RandomFadeInText from './RandomFadeInText.svelte';
	let title;
	let col1;
</script>

<div class="container">
	<IntersectionObserver once element={title} let:intersecting>
		<div bind:this={title}>
			{#if intersecting}
				<h1
					class="title"
					in:fade={{
						duration: 500 + Math.random() * 50,
						delay: Math.max(Math.random() * 40 + 1000, 500)
					}}
				>
					Tchnlgy
				</h1>
			{/if}
		</div>
	</IntersectionObserver>

	<div class="spacer"></div>

	<IntersectionObserver once element={col1} let:intersecting>
		<div bind:this={col1} class="subgrid">
			{#if intersecting}
				<div class="col1">
					<h4
						class="col-title"
						in:fade={{
							duration: 500 + Math.random() * 50,
							delay: Math.max(Math.random() * 1000 + 1000, 500)
						}}
					>
						frnt end
					</h4>

					<RandomFadeInText>react</RandomFadeInText>
					<RandomFadeInText>svelte</RandomFadeInText>
					<RandomFadeInText>vue</RandomFadeInText>
					<br />
					<RandomFadeInText>three.js</RandomFadeInText>
					<RandomFadeInText>glsl</RandomFadeInText>
					<RandomFadeInText>webgl</RandomFadeInText>
					<br />
					<RandomFadeInText>sass</RandomFadeInText>
					<RandomFadeInText>less</RandomFadeInText>
					<RandomFadeInText>tailwind</RandomFadeInText>
				</div>

				<div class="col2">
					<h4
						class="col-title"
						in:fade={{
							duration: 500 + Math.random() * 50,
							delay: Math.max(Math.random() * 1000 + 500, 500)
						}}
					>
						bck end
					</h4>

					<RandomFadeInText>node</RandomFadeInText>
					<RandomFadeInText>docker</RandomFadeInText>
					<RandomFadeInText>bun</RandomFadeInText>
					<br />
					<RandomFadeInText>express</RandomFadeInText>
					<RandomFadeInText>django</RandomFadeInText>
					<RandomFadeInText>fastapi</RandomFadeInText>
					<br />
					<RandomFadeInText>google cloud</RandomFadeInText>
					<RandomFadeInText>mondodb</RandomFadeInText>
					<RandomFadeInText>postgres</RandomFadeInText>
					<RandomFadeInText>firebase</RandomFadeInText>
				</div>

				<div class="col3">
					<h4
						class="col-title"
						in:fade={{
							duration: 500 + Math.random() * 50,
							delay: Math.max(Math.random() * 1000 + 1000, 500)
						}}
					>
						ntve
					</h4>

					<RandomFadeInText>iOS (Swift / SwiftUI / ObjectiveC)</RandomFadeInText>
					<RandomFadeInText>Android (Kotlin / Java )</RandomFadeInText>
					<RandomFadeInText>React Native</RandomFadeInText>
				</div>

				<div class="col4">
					<h4
						class="col-title"
						in:fade={{
							duration: 500 + Math.random() * 50,
							delay: Math.max(Math.random() * 1000 + 1000, 500)
						}}
					>
						dsgn
					</h4>

					<RandomFadeInText>i dabble...</RandomFadeInText>
					<RandomFadeInText>but better every day</RandomFadeInText>
					<RandomFadeInText>i did dsgn this site</RandomFadeInText>
				</div>
			{/if}
		</div>
	</IntersectionObserver>
</div>

<style>
	.container {
		grid-column: 2/10;
		grid-row: 2;
		display: grid;
		grid-template-columns: repeat(8, 1fr);
		grid-gap: 2rem;
		margin-bottom: 10rem;
		position: relative;
	}
	.subgrid {
		grid-column: 1/10;
		display: grid;
		grid-row: 2;
		grid-template-columns: repeat(8, 1fr);
		grid-gap: 2rem;
	}

	.title {
		text-transform: lowercase;
		font-weight: 600;
		font-size: 8rem;
		letter-spacing: -4.8px;
		margin-bottom: 5rem;
		grid-column: 1/9;
	}

	.spacer {
		width: 100%;
		height: 1px;
		background: var(--primary);
		grid-column: 1/9;
		grid-row: 2;
		margin-bottom: 5rem;
	}

	.col-title {
		font-size: 2.4rem;
		font-weight: 600;
		letter-spacing: -1.44px;
		margin-bottom: 2.5rem;
	}
	.tech {
		font-size: 1.6rem;
		line-height: 140%;
		letter-spacing: -0.32px;
		margin: 0;
		padding: 0;
		text-transform: lowercase;
	}

	.col1 {
		grid-column: 1/3;
	}
	.col2 {
		grid-column: 3/5;
	}
	.col3 {
		grid-column: 5/7;
	}
	.col4 {
		grid-column: 7/9;
	}
	.col1,
	.col2,
	.col3,
	.col4 {
		/*		background: var(--accent);*/
		margin-bottom: 10rem;
	}

	@media (min-width: 1440px) {
		.title {
			font-size: 10rem;
		}
	}
</style>
