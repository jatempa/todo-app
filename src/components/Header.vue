<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
  },
};
</script>

<template>
  <h1>{{ title }}</h1>
</template>
