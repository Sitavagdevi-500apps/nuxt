<template>
  <NotesMain
    :url="url"
    entity="RESPONSES"
    :entityId="1"
    :projectId="1"
    :editUrl="editUrl"
  />
</template>
<script setup lang="ts">
// Notes json
const url =
  "https://v1-orm-lib.mars.hipso.cc/notes/entity/RESPONSES/1?project_id=1&offset=0&limit=100&sort_column=id&sort_direction=desc";
const editUrl = "https://v1-orm-lib.mars.hipso.cc/notes";
</script>
