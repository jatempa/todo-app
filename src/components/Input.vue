<script>
export default {
  emits: ['onChangeInput'],
};
</script>

<template>
  <input @input="$emit('onChangeInput', $event.target.value)" type="text" />
</template>

<style scoped>
input {
  font-size: 2rem;
  outline: none;
}
</style>
