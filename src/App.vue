<script>
import Card from './components/Card.vue';
import Header from './components/Header.vue';
import Input from './components/Input.vue';

export default {
  components: {
    Card,
    Header,
    Input,
  },
  data() {
    return {
      message: 'x',
    };
  },
  methods: {
    handleUpdate(item) {
      console.log(item);
    },
  },
};
</script>

<template>
  <Card>
    <Header title="Todo List" />
    <Input v-model="message" @onChangeInput="handleUpdate" />
  </Card>
</template>
