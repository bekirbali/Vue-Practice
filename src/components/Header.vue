<template>
  <header>
    <h1>Header</h1>
    <p>Count: {{ count }}</p>
  </header>
</template>

<style scoped>
header {
  font-size: 2rem;
  color: #bfbf;
}
</style>

<script>
export default {
  props: {
    count: {
      type: Number,
      required: true,
    },
  },
  created() {},
};
</script>
