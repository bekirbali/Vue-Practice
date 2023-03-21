<template>
  <div>
    <div :key="task.id" v-for="task in props.tasks">
      {{ task.text }}
    </div>
  </div>
</template>

<script setup>
import Task from "./Task.vue";
import { defineProps } from "vue";
const props = defineProps(["tasks"]);
console.log(props.tasks);

components: {
  Task;
}
</script>
