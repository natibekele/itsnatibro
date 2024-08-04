<script>
	import { onMount } from 'svelte';
	import anime from 'animejs';
	let myShadow;
	onMount(() => {
		document.addEventListener('mousemove', updateShadowPosition);
	});

	function updateShadowPosition(e) {
		let x = e.clientX - 16;
		let y = e.clientY - 16;

		anime({
			targets: myShadow,
			translateX: `${x}`,
			translateY: `${y}`,
			easing: 'easeOutSine',
			duration: 100,
			opacity: 0.6
		});
	}
</script>

<div class="shadow" bind:this={myShadow}></div>

<style type="text/css">
	.shadow {
		position: fixed;
		top: 0;
		left: 0;
		height: 32px;
		width: 32px;
		border-radius: 50%;
		background: var(--accent);
		z-index: 10;
		pointer-events: none;
		/*		opacity: 1;*/
		/*		mix-blend-mode: color-dodge;*/
		/*		transition: ease-out 0.2s;*/
	}

	@media (max-width: 760px) {
		.shadow {
			display: none;
		}
	}
</style>
