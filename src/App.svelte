<script lang="ts">
  import "svelte-golden-layout/css/themes/goldenlayout-light-theme.css";
  import GoldenLayout from "svelte-golden-layout";

  import Viewport from "./Viewport.svelte";
  import Settings from "./Settings.svelte";

  const components = { Viewport, Settings };

  const layout = {
    root: {
      type: "row",
      content: [
        {
          type: "component",
          componentType: "Viewport",
          componentState: {
            someProp: 1,
            anotherProp: 1,
          },
        },
        {
          type: "component",
          componentType: "Settings",
        },
        {
          type: "component",
          componentType: "Settings",
        },
        {
          type: "component",
          componentType: "Settings",
        },
        {
          type: "component",
          componentType: "Settings",
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
