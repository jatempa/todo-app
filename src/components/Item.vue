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
  <span>{{ item.title }}</span>
</template>

<style scoped>
span {
  overflow-wrap: break-word;
}
</style>
