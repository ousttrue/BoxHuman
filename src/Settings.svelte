<script lang="ts">
  import { Checkbox, Pane, ThemeUtils, Slider } from "svelte-tweakpane-ui";

  export let bones: string[] = [];

  console.log("componentState", bones);

  const values: Record<string, number> = {};
  for (const bone of bones) {
    values[bone] = 1.0;
  }
</script>

<Pane theme={ThemeUtils.presets.light} position="inline" title="OrbitControls">
  {#each bones as bone}
    <Slider
      label={bone}
      bind:value={values[bone]}
      min={0.1}
      max={2}
      step={0.1}
    />
  {/each}
</Pane>
