<script>
export default {
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
};
</script>

<template>
  <ul>
    <li v-for="item in items" :key="item.id">
      {{ item }}
    </li>
  </ul>
</template>
