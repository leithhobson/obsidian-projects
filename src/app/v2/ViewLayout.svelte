<script lang="ts">
  import type { DataFrame } from "src/lib/data";
  import type { ViewDefinition } from "src/settings/settings";

  export let view: ViewDefinition | undefined;
  export let frame: DataFrame;
</script>

{#if view}
  <div>
    <input bind:value={view.name} />
  </div>

  <div>
    <p>{view.name}</p>
    <p>{JSON.stringify(frame.records)}</p>
  </div>
{/if}
