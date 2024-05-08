<script>
	import { onMount } from 'svelte';
	const images = [
		'/images/cover.jpg',
		'images/table.jpg',
		'images/okinawa.jpg',
		'images/vietnam.jpg',
		// 'images/okinawa2.jpg',
		'images/me.jpg',
		'images/okinawa3.jpg',
		'images/central.jpg',
		'images/okinawa4.jpg',
		'images/market.jpg'
	];

	onMount(() => {
		// startReel();
	});

	var index = 0;

	let interval;
	function startReel() {
		interval = setInterval(() => {
			index++;
		}, 175);
	}
	function pauseReel() {
		clearInterval(interval);
	}
</script>

<img
	src={images[index % images.length]}
	alt="portrait reel"
	on:mouseenter={startReel}
	on:mouseleave={pauseReel}
/>

<style>
	img {
		height: 100%;
		width: 100%;
		object-fit: cover;
		grid-column: 1/11;
		grid-row: 1;
		aspect-ratio: 16/19;
	}
</style>
