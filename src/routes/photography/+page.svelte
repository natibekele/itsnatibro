<script type="text/javascript">
	import { fade, scale } from "svelte/transition";
</script>
<div class="prog">
	<h3 in:fade> work in progress</h3>

	<p in:fade> i'm building something new for this space. sadly it's not finished yet. come & check back soon! </p>
</div>

<style>
	div {
		font-family: 'Manrope';
		padding: 1.5rem 1rem;
/*		background: var(--dynamic-orange);*/
		height: 90vh;
		width: 100%;
/*		color: var(--white);*/
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