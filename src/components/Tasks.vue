<template>
  <div>
    <h1 @click="show">hello</h1>
    <div :key="task.id" v-for="task in tasks">
      <Task
        @delete-task="$emit('delete-task', task.id)"
        @update-task="$emit('update-task', task.id)"
        :task="task"
      />
    </div>
  </div>
</template>

<script>
import Task from "./Task.vue";
export default {
  name: "Tasks",
  props: {
    tasks: {
      type: Array,
    },
  },
  methods: {
    show() {
      console.log(this.tasks);
    },
  },
  components: {
    Task,
  },
  emits: ["delete-task", "update-task"],
};
</script>
