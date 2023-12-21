<script>
  import { onMount } from "svelte"
  import { Group, BufferGeometry, Float32BufferAttribute } from 'three'
  import { T, forwardEventHandlers } from '@threlte/core'

  const size = 20
  const count = size ** 3

  const positions = new Float32Array(count * 3)

  function linearWithNoise(val, axisScale = 25) {
    const m = 0.1;
    return Math.random() * axisScale - Math.random() * 2
  }
  // 3D math squiggles
  for (let i = 0; i < count; i++) {
    // 1D to 3D array
    let x = linearWithNoise(i)
    let y = linearWithNoise(i, 20)
    let z = linearWithNoise(i)

    //x
    positions[i * 3 + 0] = x
    //y
    positions[i * 3 + 1] = y
    //z
    positions[i * 3 + 2] = z
  }

</script>

<T.Points {...$$restProps}>
  <T.BufferGeometry>
      <T.BufferAttribute  args={[positions, 3]}
        attach={(parent, self) => {
          parent.setAttribute('position', self)
          return () => {
            // cleanup function called when ref changes or the component unmounts
            // https://threlte.xyz/docs/reference/core/t#attach
          }
        }}
       />
  </T.BufferGeometry>
  <T.PointsMaterial color={Math.random() < 0.75 ? "#2a3d45" : "#71f79f"} sizeAttenuation={true} size={0.2} />
</T.Points>