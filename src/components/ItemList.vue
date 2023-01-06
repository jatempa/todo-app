<script>
import Item from './Item.vue';
import Mark from './Mark.vue';

export default {
  components: {
    Item,
    Mark,
  },
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
  methods: {
    updateStatus(id) {
      const index = this.items.findIndex((item) => item.id === id);
      this.items[index].done = !this.items[index].done;
    },
  },
};
</script>

<template>
  <ul>
    <li class="item-container" v-for="item in items" :key="item.id">
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

.item-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
