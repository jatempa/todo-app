<script>
import Item from './Item.vue';

export default {
  components: {
    Item,
  },
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
      <Item :item="item" />
    </li>
  </ul>
</template>

<style scoped>
ul {
  padding: 0px;
}

li {
  padding: 0px;
  text-align: left;
  list-style-position: inside;
  list-style-type: decimal;
  font-size: 1.5rem;
}
</style>
