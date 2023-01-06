<script>
export default {
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
  emits: ['update-status'],
};
</script>

<template>
  <div
    class="box"
    @click="$emit('update-status', item)"
    :class="this.item.done ? 'done' : ''"
  />
</template>

<style scoped>
.box {
  height: 30px;
  width: 30px;
  background-color: rgb(236, 233, 233);
}
.done {
  background-color: yellowgreen;
}
</style>
