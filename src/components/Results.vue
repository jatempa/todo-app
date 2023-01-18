<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  tasks: {
    type: Object,
    required: true,
  },
});
</script>

<template>
  <div v-if="tasks.all > 0">
    <hr />
    <div class="container">
      <span><strong>Total:</strong> {{ tasks.all }}</span>
      <span><strong>Complete:</strong> {{ tasks.complete }}</span>
      <span><strong>Incomplete:</strong> {{ tasks.incomplete }}</span>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  justify-content: space-between;
}
</style>
