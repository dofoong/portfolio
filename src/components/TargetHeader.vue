<template>
  <div class="header col-3 row items-center" style="font-size: 2rem; color: darkslateblue">
    <div style="width: 5px; background-color: darkslateblue; height: 50px" class="q-mr-sm"></div>
    <div style="font-weight: 500">
      {{ props.header }}
    </div>
  </div>
</template>
<script setup lang="ts">
const props = defineProps({
  header: {
    type: String,
    required: true,
  },
});
</script>
