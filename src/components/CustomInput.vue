<script>
export default {
  props: ['modelValue'],
  emits: ['update:modelValue', 'handle-change'],
};
</script>

<template>
  <input
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
    @keyup.enter="$emit('handle-change')"
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
