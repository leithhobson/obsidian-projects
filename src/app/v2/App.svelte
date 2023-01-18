<script lang="ts">
  import ProjectSwitcher from "./ProjectSwitcher.svelte";
  import {
    DEFAULT_PROJECT,
    DEFAULT_VIEW,
    type ProjectDefinition,
  } from "src/settings/settings";
  import ProjectLayout from "./ProjectLayout.svelte";

  let projects: ProjectDefinition[] = [
    {
      ...DEFAULT_PROJECT,
      id: "project1",
      name: "Project 1",
      views: [
        { ...DEFAULT_VIEW, id: "view1", name: "View 1", type: "table" },
        { ...DEFAULT_VIEW, id: "view2", name: "View 2", type: "table" },
        { ...DEFAULT_VIEW, id: "view3", name: "View 3", type: "table" },
      ],
    },
    { ...DEFAULT_PROJECT, id: "project2", name: "Project 2" },
  ];
</script>

<ProjectSwitcher bind:projects let:selected>
  <ProjectLayout bind:project={projects[selected]} />
</ProjectSwitcher>
