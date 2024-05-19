<script>
	import { fade } from 'svelte/transition';
</script>

<p
	class="text"
	in:fade={{
		duration: 500 + Math.random() * 50,
		delay: Math.max(Math.random() * 1000 + 1000, 500)
	}}
>
	<slot />
</p>

<style>
	.text {
		font-size: 1.6rem;
		line-height: 140%;
		letter-spacing: -0.32px;
		margin: 0;
		padding: 0;
		text-transform: lowercase;
	}
</style>
