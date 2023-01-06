<script>
import Card from './components/Card.vue';
import Header from './components/Header.vue';
import CustomTaskInput from './components/CustomTaskInput.vue';
import ItemList from './components/ItemList.vue';
import { v4 as uuidv4 } from 'uuid';

export default {
  components: {
    Card,
    CustomTaskInput,
    Header,
    ItemList,
  },
  data() {
    return {
      items: [],
    };
  },
  methods: {
    handleChange(item) {
      if (!item || item.length === 0) return;

      const newItem = {
        id: uuidv4(),
        title: item,
        done: false,
      };

      this.items.push(newItem);
    },
  },
};
</script>

<template>
  <Card>
    <Header>To Do</Header>
    <CustomTaskInput @handle-change="handleChange" />
    <ItemList :items="items" />
  </Card>
</template>
