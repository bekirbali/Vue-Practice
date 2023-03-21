<template>
  <div :class="[task.reminder ? 'reminder' : 'task', 'fixed']">
    <h3 @dblclick="updateHandler(task.id)">
      {{ task.text }} {{ task.day }}
      <span @click="deleteHandler(task.id)">(X)</span>
    </h3>
  </div>
</template>

<script>
export default {
  props: {
    task: Object,
  },
  methods: {
    deleteHandler(id) {
      console.log(id);
      this.$emit("delete-task", id);
    },
    updateHandler(id) {
      console.log(id);
      this.$emit("update-task", id);
    },
  },
};
</script>

<style scoped>
.task {
  background-color: rgb(148, 148, 142);
  color: black;
}
.fixed {
  padding: 0.5rem;
  text-align: center;
  border: 1px solid rgb(31, 36, 41);
}
.reminder {
  background-color: rgb(11, 99, 78);
  border-left: 4px solid blue;
}
span {
  color: red;
  cursor: pointer;
}
</style>
