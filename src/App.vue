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

      const id = uuidv4();
      const newItem = {
        id,
        description: item,
      };

      this.items.push(newItem);
    },
  },
};
</script>

<template>
  <Card>
    <Header title="Todo" />
    <CustomTaskInput @handle-change="handleChange" />
    <ItemList :items="items" />
  </Card>
</template>
