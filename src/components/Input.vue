<script>
export default {
  emits: ['onChangeInput'],
};
</script>

<template>
  <input @keyup.enter="$emit('onChangeInput', $event.target.value)" type="text" />
</template>

<style scoped>
input {
  font-size: 2rem;
  outline: none;
}
</style>
