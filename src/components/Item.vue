<script>
export default {
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
};
</script>

<template>
  <span>{{ item.description }}</span>
</template>

<style scoped>
span {
  overflow-wrap: break-word;
}
</style>
