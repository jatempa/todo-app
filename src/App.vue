<script>
import { v4 as uuidv4 } from 'uuid';
import Card from './components/Card.vue';
import Header from './components/Header.vue';
import CustomTaskInput from './components/CustomTaskInput.vue';
import ItemList from './components/ItemList.vue';
import Results from './components/Results.vue';

export default {
  components: {
    Card,
    CustomTaskInput,
    Header,
    ItemList,
    Results,
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
  computed: {
    tasksByStatus() {
      const complete = this.items.filter((item) => item.done).length;
      const incomplete = this.items.length - complete;

      return {
        all: this.items.length,
        complete,
        incomplete,
      };
    },
  },
};
</script>

<template>
  <Card>
    <Header>To Do</Header>
    <CustomTaskInput @handle-change="handleChange" />
    <ItemList :items="items" />
    <Results :tasks="tasksByStatus" />
  </Card>
</template>
