<script lang="ts">
  import type { ProjectDefinition } from "src/settings/settings";
  import FrameProvider from "./FrameProvider.svelte";
  import ViewLayout from "./ViewLayout.svelte";
  import ViewSwitcher from "./ViewSwitcher.svelte";

  export let project: ProjectDefinition | undefined;
</script>

{#if project}
  <FrameProvider dataSource={project.dataSource} let:frame>
    <div>
      <input bind:value={project.name} />
    </div>

    <div>
      <p>{project.name}</p>
    </div>

    <div>
      <ViewSwitcher bind:views={project.views} let:selected>
        <ViewLayout bind:view={project.views[selected]} {frame} />
      </ViewSwitcher>
    </div>
  </FrameProvider>
{/if}
