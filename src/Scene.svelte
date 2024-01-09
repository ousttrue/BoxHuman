<script lang="ts">
  import { OrbitControls } from "@threlte/extras";
  import { T } from "@threlte/core";
  import * as THREE from "three";
</script>

<T.PerspectiveCamera makeDefault fov={80} position={[5, 5, 5]}>
  <OrbitControls
    mouseButtons={{
      LEFT: THREE.MOUSE.DOLLY,
      MIDDLE: THREE.MOUSE.PAN,
      RIGHT: THREE.MOUSE.ROTATE,
    }}
  />
</T.PerspectiveCamera>

<T.DirectionalLight position.y={10} position.z={10} />
<T.AmbientLight intensity={0.3} />

<T.GridHelper size={10} division={10} />
<T.Mesh position={[0, 0.5, 0]}>
  <T.BoxGeometry args={[1, 1, 1]} />
  <T.MeshStandardMaterial color="red" />
</T.Mesh>
