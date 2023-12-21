<script>
	import anime from "animejs"
	import { onMount } from "svelte"

	onMount(_ => {
		setTimeout(_ => {
			coverTimeline();
		}, 2000)
	})
	function coverTimeline() {
		var timeline = anime.timeline({
				easing: 'easeInOutSine',
				duration: 500,
			});

			timeline.add({
				targets: '.tl',
				keyframes: [
					{ translateX: '100%' },
					{ translateY: '100%' }
				]
			})
			.add({
				targets: '.tr',
				keyframes: [
					{ translateY: '100%' },
					{ translateX: '-100%' }
				]
			})
			.add({
				targets: '.br',
				keyframes: [
					{ translateX: '-100%' },
					{ translateY: '-100%' }
				]
			})
			.add({
				targets: '.bl',
				keyframes: [
					{ translateY: '-100%' },
					{ translateX: '100%' }
				]
			})
			.add({
				targets: '.cover',
				translateY: '-100%',
				duration: 1000
			})
		}
</script>

<div class="cover">
	<div class="rect-container">
		<div class="rect tl"></div>
		<div class="rect tr"></div>
		<div class="rect c"></div>
		<div class="rect br"></div>
		<div class="rect bl"></div>
	</div>
</div>

<style type="text/css">
	.cover {
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		z-index: 100;
		background: var(--primary);
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.rect-container {
		height: 10rem;
		width: 10rem;
		position: relative;
	}
	.rect {
		height: 10rem;
		width: 10rem;
		background: var(--base);
		position: absolute;
	}
	.tl {
		left:  -100%;
		top: -100%;
		background: var(--accent);
	}
	.tr {
		left: 100%;
		top: -100%;
	}
	.c {

	}
	.br {
		left:  100%;
		top: 100%;
	}
	.bl {
		left:  -100%;
		top: 100%;
}
</style>