<script>
export default {
  data: () => ({
    task: '',
  }),
  emits: ['handle-change'],
  methods: {
    addTask() {
      this.$emit('handle-change', this.task);
      this.task = '';
    },
  },
};
</script>

<template>
  <input
    :value="task"
    @input="task = $event.target.value"
    @keyup.enter="addTask"
  />
</template>

<style scoped>
input {
  font-size: 2rem;
  outline: none;
}
</style>
