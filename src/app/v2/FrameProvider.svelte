<script lang="ts">
  import { emptyDataFrame } from "src/lib/data";
  import type { DataSource } from "src/settings/v2/settings";

  export let dataSource: DataSource;

  $: frame = query(dataSource);

  function query(dataSource: DataSource) {
    console.log("querying", dataSource.kind);
    return emptyDataFrame;
  }
</script>

<slot {frame} />
