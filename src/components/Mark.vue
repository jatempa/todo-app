<script>
export default {
  props: {
    done: {
      type: Boolean,
      required: true,
    },
  },
};
</script>

<template>
  <div class="box" :class="this.done ? 'done' : ''" />
</template>

<style scoped>
.box {
  float: right;
  vertical-align: middle;
  height: 30px;
  width: 30px;
  background-color: rgb(236, 233, 233);
}

.done {
  background-color: yellowgreen;
}
</style>
