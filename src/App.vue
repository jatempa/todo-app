<script>
import { v4 as uuidv4 } from 'uuid';
import Card from './components/Card.vue';
import Header from './components/Header.vue';
import CustomInput from './components/CustomInput.vue';
import ItemList from './components/ItemList.vue';
import Results from './components/Results.vue';

export default {
  components: {
    Card,
    CustomInput,
    Header,
    ItemList,
    Results,
  },
  data() {
    return {
      items: [],
      task: '',
    };
  },
  methods: {
    handleChange() {
      if (this.task.length === 0) return;

      const newItem = {
        id: uuidv4(),
        title: this.task,
        done: false,
      };

      this.items.push(newItem);
      this.task = '';
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
    <CustomInput v-model="task" @handle-change="handleChange" />
    <ItemList :items="items" />
    <Results :tasks="tasksByStatus" />
  </Card>
</template>
