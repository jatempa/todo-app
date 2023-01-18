<script setup>
import Item from './Item.vue';
import Mark from './Mark.vue';

const props = defineProps({
  items: {
    type: Array,
    required: true,
  },
});

const updateStatus = (id) => {
  const index = props.items.findIndex((item) => item.id === id);
  props.items[index].done = !props.items[index].done;
};
</script>

<template>
  <ul>
    <li class="item-container" v-for="item in props.items" :key="item.id">
      <Item :item="item" />
      <Mark :done="item.done" @click="updateStatus(item.id)" />
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
  margin-bottom: 15px;
}
</style>
