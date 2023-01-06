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
    placeholder="Enter your task ..."
  />
</template>

<style scoped>
input {
  width: 100%;
  font-size: 2rem;
  padding: 0px;
  border: 0px;
  outline: none;
}
</style>
