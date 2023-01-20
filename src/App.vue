<script setup>
import { computed } from '@vue/reactivity';
import { v4 as uuidv4 } from 'uuid';
import { reactive } from 'vue';
import Card from './components/Card.vue';
import CustomInput from './components/CustomInput.vue';
import Header from './components/Header.vue';
import ItemList from './components/ItemList.vue';
import Results from './components/Results.vue';

const state = reactive({
  items: [],
  task: '',
});

const handleChange = () => {
  if (state.task.length === 0) return;

  const newItem = {
    id: uuidv4(),
    title: state.task,
    done: false,
  };

  state.items.push(newItem);
  state.task = '';
};

const tasksByStatus = computed(() => {
  const complete = state.items.filter((item) => item.done).length;
  const incomplete = state.items.length - complete;

  return {
    all: state.items.length,
    complete,
    incomplete,
  };
});
</script>

<template>
  <Card>
    <Header>To Do</Header>
    <form @submit.prevent="handleChange">
      <CustomInput v-model="state.task" />
    </form>
    <ItemList :items="state.items" />
    <Results :tasks="tasksByStatus" />
  </Card>
</template>
