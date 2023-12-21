<script>
	import { Canvas } from "@threlte/core"
	import { World } from "@threlte/rapier"
	import { HTML } from "@threlte/extras"
	import SwarmScene from "$lib/SwarmScene.svelte"
</script>

<div>
	<Canvas>
		<World>
			<SwarmScene />
		      <HTML
		        slot="fallback"
		        transform
		      >
		        <p>
		          It seems your browser<br />
		          doesn't support WASM.<br />
		          I'm sorry.
		        </p>
	      </HTML>
		</World>
	</Canvas>
</div>

<style>
	div {
		height: 90vh;
		width: 100vw;
	}
</style>