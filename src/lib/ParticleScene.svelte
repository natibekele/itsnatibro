<script>
	import { T, useTask } from '@threlte/core'
	import Slash from "./Slash.svelte"
	import ManualSlash from "./ManualSlash.svelte"
	import Squiggles from "./Squiggles.svelte"
	import { interactivity } from "@threlte/extras"

	interactivity();

	let rotation = 0;
	let mousePos = { x: 0, y: 0 }
	let lookAt = [0, 8, 0];

	useTask((delta) => {
		rotation += delta * 0.125
		// lookAt = [ 0 + (mousePos.x * 0.1 ), 8 + (mousePos.y * 0.01), 0 ]
	})

	document.addEventListener('mousemove', e => {
		mousePos.x = e.x;
		mousePos.y = e.y;
	})
</script>

<T.PerspectiveCamera
	makeDefault
	position={[5, 10, 0]}
	rotation.y={mousePos.x * 0.00005 * Math.PI }
	rotation.x={mousePos.y * 0.00005 * Math.PI}
	on:create={({ ref}) => {
		ref.lookAt(0,10,0)
	}}
/>

<T.DirectionalLight position={[0, 10, 10]} intensity={2} color="red"/>
<!-- 
<T.Mesh position.y={1}>
<T.BoxGeometry args={[1,2,1]}/>
<T.MeshBasicMaterial color="hotpink"/>
</T.Mesh> -->

<!-- <Squiggles /> -->
<ManualSlash rotation.y={rotation} rotation.z={Math.PI/8}/>
<ManualSlash rotation.y={rotation} rotation.z={Math.PI/8} position.x={-5}/>
<ManualSlash rotation.y={rotation} rotation.z={Math.PI/8} position.x={5}/>
<!-- <Slash rotation.y={rotation}/>
<Slash rotation.y={rotation} position.x={8}/>
<Slash rotation.y={rotation} position.x={-8}/> -->