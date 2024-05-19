<script>
	import { fly, fade } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
	import anime from 'animejs';
	import { onMount } from 'svelte';
	export let text;
	export let initialDelay;
	let animate = false;

	onMount(() => {
		animate = true;
	});
</script>

<div class="container-wordsplit">
	{#each text.split(' ') as word, i}
		{#if animate}
			<span class="mask">
				<span
					class="word"
					in:fade={{
						duration: 500 + Math.random() * 50,
						delay: Math.max(i * Math.random() * 40 + 1000 + initialDelay, 500)
					}}
				>
					{word}&nbsp;
				</span>
			</span>
		{/if}
	{/each}
</div>

<style>
	.container-wordsplit {
		display: flex;
		flex-wrap: wrap;
		width: 100%;
		/*		grid-column: 1/11;*/

		/*		width: auto;*/
	}
	.mask {
		/*		width: --webkit-fill-available;*/
		/*		height: 1.6rem;*/
		overflow: hidden;
		display: block;
		/*align-items: center;
		justify-content: center;*/
		/*		flex: 1;*/
		position: relative;
	}

	.word {
		/*		position: absolute;*/
		/*height: 100%;
		width: 100%;*/
		margin: 0;
		top: 0px;
		display: inline-block;
		font-size: 1.6rem;
		font-weight: 400;
		letter-spacing: -0.32px;
		line-height: 1.5;
		/*		transform: translateY(100%);*/
	}
</style>
