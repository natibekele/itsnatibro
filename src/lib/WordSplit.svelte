<script>
	import {fly, fade} from "svelte/transition"
	import { quintOut } from 'svelte/easing';
	import anime from "animejs"
	import { onMount } from "svelte"
	export let text;
	export let initialDelay;
	let animate = false;

	onMount(_ => {
		animate = true;
	})

</script>


<div class="container-wordsplit">
	{#each text.split(' ') as word, i}
	 {#if animate}
		<span class="mask">
			<span class="word"
			in:fly={{ y: "100%", duration: 500, delay: initialDelay + 30 * i}}>
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
		width: 100%
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
		top: 0px;
		display: inline-block;
		font-size: 1.8rem;
		font-weight: normal;
		letter-spacing: 1.2%;
/*		transform: translateY(100%);*/
	}
</style>


