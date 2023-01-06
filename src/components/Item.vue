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
  <span :class="item.done ? 'done' : ''">{{ item.title }}</span>
</template>

<style scoped>
span {
  overflow-wrap: break-word;
}

.done {
  text-decoration-line: line-through;
}
</style>
