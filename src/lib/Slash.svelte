<!--
Auto-generated by: https://github.com/threlte/threlte/tree/main/packages/gltf
Command: npx @threlte/gltf@2.0.1 static/models/slash.glb
-->

<script>
  import { onMount } from "svelte"
  import { Group, BufferGeometry } from 'three'
  import { T, forwardEventHandlers } from '@threlte/core'
  import { useGltf } from '@threlte/extras'

  export const ref = new Group()

  const gltf = useGltf('/models/slash.glb')

  const component = forwardEventHandlers()

  const vertices = [];
  let randomized = false;

  onMount(() => {
    console.log(gltf?.nodes?.Cube.geometry)
  })

  function randomizeGeometry(geometry) {
    // const { position } = geometry.attributes
    // for (var i = 0; i < position.count * 3 < i+3;) {
      // position.array[i] += (Math.random ())
      // vertices[ i+1 ] = position.array[i + 1 ]
      // position.array[i + 2] += (Math.random() * 2 - 1 )
    // }

    // geometry.attributes.position.needsUpdate = true
    // geometry.attributes.position.array = vertices;
    // // geometry.attributes.position.array = vertices;

    // console.log(vertices.length, vertices[1000])
    // console.log(geometry)
    // // geometry.setAttribute('position', new Float32BufferAttribute( vertices, 3))
    randomizing = true
    console.log(randomized, 'randomized')
    return geometry
  }

  // console.log(gl)
</script>

<T is={ref} dispose={false} {...$$restProps} bind:this={$component}>
  {#await gltf}
    <slot name="fallback" />
  {:then gltf}
    <T.Points
      geometry={gltf.nodes.Cube.geometry}
      position={[0, 5.63, 0]}
      scale={[1, 5.36, 1]}
    >
    <T.PointsMaterial color="#2a3d45" sizeAttenuation={true} size={0.2}/>
  </T.Points>
  {:catch error}
    <slot name="error" {error} />
  {/await}

  <slot {ref} />
</T>
