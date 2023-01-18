<script lang="ts">
  import type { ProjectDefinition } from "obsidian-projects-types";
  import { Select } from "obsidian-svelte";

  export let projects: ProjectDefinition[];

  $: options = projects.map((project, index) => ({
    label: project.name,
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
