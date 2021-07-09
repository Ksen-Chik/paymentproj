<template>
  <div class="pagination">
    <div v-for="(item, idx) in list" :key="idx">{{ idx + 1 }}-{{ item }}</div>
  </div>
</template>

<script>
export default {
  name: "Pagination",
  props: {
    list: {
      type: Array,
      default: () => [],
    },
  },
  data() {
    return {};
  },
};
</script>

<style>
</style>