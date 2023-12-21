<script type="text/javascript">
	import { fade, scale } from "svelte/transition";
</script>
<div class="proj ">
	<h3 in:fade> work in progress</h3>

	<p in:fade> i'm building something new for this space. sadly it's not finished yet. come & check back soon! </p>
</div>

<style>
	div {
		font-family: 'Manrope';
		padding: 1.5rem 1rem;
/*		background: var(--tea-rose);*/
		height: 90vh;
		width: 100%;
		margin: 0 2rem;
	}
	h3 {
		font-size: 2.4rem;
		letter-spacing: -0.2rem;
		margin: 0;
		font-weight: 500;
	}
	p {
		font-size: 1.6rem;
	}
</style>