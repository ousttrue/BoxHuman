<script lang="ts">
  import "svelte-golden-layout/css/themes/goldenlayout-light-theme.css";
  import GoldenLayout from "svelte-golden-layout";
  import type { LayoutConfig } from "golden-layout";
  import Viewport from "./Viewport.svelte";
  import Settings from "./Settings.svelte";

  const components: { [key: string]: any } = { Viewport, Settings };

  const layout: LayoutConfig = {
    root: {
      type: "row",
      content: [
        {
          type: "component",
          componentType: "Viewport",
          componentState: {},
        },
        {
          title: "spine",
          type: "component",
          componentType: "Settings",
          componentState: {
            bones: ["hips", "spine", "chest", "upperChest", "neck", "head"],
          },
        },
        {
          title: "arm",
          type: "component",
          componentType: "Settings",
          componentState: {
            bones: ["shoulder", "upperArm", "lowerArm", "hand"],
          },
        },
        {
          title: "leg",
          type: "component",
          componentType: "Settings",
          componentState: {
            bones: ["upperLeg", "lowerLeg", "foot", "toes"],
          },
        },
        {
          title: "fingers",
          type: "component",
          componentType: "Settings",
          componentState: {
            bones: [
              "thumbMetacarpal",
              "thumbProximal",
              "thumbDistal", // thumb
              "indexProximal",
              "indexIntermediate",
              "indexDistal", // index
              "middleProximal",
              "middleIntermediate",
              "middleDistal", // middle
              "ringProximal",
              "ringIntermediate",
              "ringDistal", // ring
              "littleProximal",
              "littleIntermediate",
              "littleDistal", // little
            ],
          },
        },
      ],
    },
  };
</script>

<div>
  <GoldenLayout config={layout} let:componentType let:componentState>
    <svelte:component this={components[componentType]} {...componentState} />
  </GoldenLayout>
</div>

<style>
  div {
    position: relative;
    height: 100%;
    width: 100%;
    background-color: rgb(14, 22, 37);
  }
</style>
