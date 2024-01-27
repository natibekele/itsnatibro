<script type="text/javascript">
	import { fade, scale, fly } from "svelte/transition";
</script>
<div class="exp">
	<h3 in:fade={{ y: 0, duration: 750, delay: 300 }}> work in progress</h3>

	<p in:fade={{ y:0, duration: 750, delay: 500 }} > i'm building something new for this space. sadly it's not finished yet. come & check back soon! </p>
</div>

<style>
	div {
		font-family: 'Manrope';
		padding: 1.5rem 0rem;
/*		background: var(--killbill-yellow);*/
		height: 90vh;
		width: 100%;
		margin: 0 2rem;
	}
	h3 {
		font-size: 3rem;
		letter-spacing: -0.28rem;
		margin: 0;
		font-weight: 700;
	}
	p {
		font-size: 1.6rem;
	}
</style>