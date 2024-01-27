<script type="text/javascript">
	import "../global.css"
	import "../fonts.css" //set up fonts
	import Header from "$lib/header.svelte"
	import MouseShadow from "$lib/MouseShadow.svelte"
	// import Cover from "$lib/Cover.svelte"
	import Footer from "$lib/footer.svelte"

	import { fly } from "svelte/transition"
	export let data;
</script>

<Header />
<MouseShadow />
<!-- {#key data.pathname} -->
<!-- <div 
	in:fly={{duration: 300, delay: 500}}
	out:fly={{duration: 300, delay: 500}}> -->
<div class="slot-container">
	<slot/>
</div>
<Footer />
<!-- {/key} -->

<!-- <SlideTransition /> -->

<style type="text/css">
	.slot-container {
		padding-top: 5.5rem;
		z-index: 1;
	}
</style>