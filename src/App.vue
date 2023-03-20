<script setup></script>

<template>
  <HelloWorld count="count" />
  <button @click="count++">Add 1</button>

  <p v-show="show">{{ title }}: {{ count }}</p>
  <button @click="changeShow">show-hide</button>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
      title: "I am the count and I am: ",
      show: true,
    };
  },
  methods: {
    changeShow() {
      this.show = !this.show;
    },
  },
};
</script>
