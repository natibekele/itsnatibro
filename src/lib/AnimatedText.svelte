<script type="module">
	import {onMount} from "svelte"
	import {fly} from "svelte/transition"
	import anime from "animejs"
	import { quintOut } from 'svelte/easing';
	export let text;

	let anotherFunction;

	// onMount(introAnimation);

	function introAnimation() {
		anime.timeline({
			easing: 'easeInOutSine',
			autoplay: true,
			duration: 500
		})
		.add({
			targets: '.p-inline',
			translateY: 0,
			easing: 'easeInOutSine'
		});
	}
</script>

<p class="p-parent">
	<span class="p-inline" 
		in:fly={{ y: "100%", duration: 500, delay: 1000, easing: quintOut }}
		out:fly={{ y: "100%", duration: 500 }}>
		{text}
	</span>
</p>

<style type="text/css">
	.p-parent {
		max-height: 40px;
		height: auto;
		position: relative;
		overflow: hidden;
	}

	.p-inline {
		font-size: 1.6rem;
		position: absolute;
		height: 100%;
		width: 100%;
		top: 0px;
	}

</style>