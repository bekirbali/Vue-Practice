<template>
  <button @click="clickHandler">{{ text }}</button>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
    },
  },
  methods: {
    clickHandler() {
      console.log("clicked");
    },
  },
};
</script>
