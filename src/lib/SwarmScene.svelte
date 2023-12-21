<script type="text/javascript">
	import { T, useTask, Canvas } from '@threlte/core'
	import { SphereGeometry, BoxGeometry } from "three"
	import Slash from "./Slash.svelte"
	import ManualSlash from "./ManualSlash.svelte"
	import Squiggles from "./Squiggles.svelte"
	import { interactivity, OrbitControls } from "@threlte/extras"
	import { World, AutoColliders, Collider, RigidBody, Attractor } from "@threlte/rapier"

	// interactivity();

	let rotation = 0;

	// useTask((delta) => {
	// 	rotation 
	// })
</script>

<T.PerspectiveCamera position={[0,5,20]} makeDefault
	on:create={({ ref}) => {
		ref.lookAt(0,0,0)
	}}>
	<OrbitControls enableZoom={false}/>
</T.PerspectiveCamera>

<!-- <T.AmbientLight color="white" /> -->
<T.DirectionalLight color="#eee5e9" position={[ 0, 5, 15]} castShadow={true} intensity={2}/>
<T.DirectionalLight color="red" position={[ 0, 10, -20]} castShadow={true} intensity={2}/>
<T.DirectionalLight color="pink" position={[ -10, 2, 0]} castShadow={true} intensity={2}/>

<T.Group position={[0, 3, 0]}>
	<RigidBody type="dynamic">
		<Collider shape="ball" args={[1,1,1]}
			restitution={0.9}
			contactForceEventThreshold={30}
		>
			<T.Mesh
				castShadow={true}
				geometry={ new SphereGeometry(1)}>
				<T.MeshToonMaterial color="#71f79f" />
			</T.Mesh>
		</Collider>
	</RigidBody>
</T.Group>
<T.Group position={[2, 3, 4]}>
	<RigidBody type="dynamic">
		<Collider shape="ball" args={[1,1,1]}
			restitution={0.9}
			contactForceEventThreshold={30}
		>
			<T.Mesh
				castShadow={true}
				geometry={ new SphereGeometry(1)}>
				<T.MeshLambertMaterial color="#71f79f" />
			</T.Mesh>
		</Collider>
	</RigidBody>
</T.Group>

<T.Group position={[-2, 8, 2]}>
	<RigidBody type="dynamic">
		<Collider shape="cuboid" args={[0.5,0.5,0.5]}
			restitution={0.9}
			contactForceEventThreshold={30}
		>
			<T.Mesh
				castShadow={true}
				geometry={ new BoxGeometry(1,1,1)}>
				<T.MeshStandardMaterial color="#71f79f" />
			</T.Mesh>
		</Collider>
	</RigidBody>
</T.Group>

<T.Group position={[0, -0.5, 0]}>
  <AutoColliders shape={'cuboid'}>
    <T.Mesh receiveShadow>
      <T.BoxGeometry args={[20, 1, 20]} receiveShadow={true}/>
      <T.MeshLambertMaterial color="#2a3d45"/>
    </T.Mesh>
  </AutoColliders>
</T.Group>

<Attractor range={20}
	strength={0.5}
	position={[ 4, 0.5, 0]}
/>
