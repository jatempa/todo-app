<template>
  <div class="card">
    <slot></slot>
  </div>
</template>

<style scoped>
.card {
  border: 1px solid black;
  padding: 20px;
  width: 500px;
  max-width: 500px;
  min-height: 300px;
}
</style>
