<script lang="ts">
  import { Select } from "obsidian-svelte";
  import type { ViewDefinition } from "src/settings/settings";

  export let views: ViewDefinition[];

  $: options = views.map((view, index) => ({
    label: view.name,
    value: index.toString(),
  }));

  let selected: number = -1;
</script>

<div>
  <Select
    value={selected.toString()}
    on:change={({ detail }) => (selected = parseInt(detail))}
    {options}
  />
</div>

<div>
  <slot {selected} />
</div>
