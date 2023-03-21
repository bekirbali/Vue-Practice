<template>
  <button @click="count++">Add 1</button>

  <p v-show="show">{{ title }}: {{ count }}</p>
  <button @click="changeShow">show-hide</button>
  <Header :count="count" />
  <Tasks @delete-task="deleteTask" @update-task="updateTask" :tasks="tasks" />
  <Button text="Add Task" />
  <Button text="Delete Task" />
  <Button text="Update Task" />
</template>

<script>
import Button from "./components/Button.vue";
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";

export default {
  data() {
    return {
      count: 0,
      title: "I am the count and I am: ",
      show: true,
      tasks: [],
    };
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Task 1",
        day: "Monday",
        reminder: true,
      },
      {
        id: 2,
        text: "Task 2",
        day: "Wednesday",
        reminder: false,
      },
      {
        id: 3,
        text: "Task 3",
        day: "Friday",
        reminder: false,
      },
    ];
  },
  components: { Header, Button, Tasks },
  methods: {
    changeShow() {
      this.show = !this.show;
      console.log(this.tasks.map((task) => task.text));
    },
    deleteTask(id) {
      console.log("task", id);
      this.tasks = this.tasks.filter((task) => task.id !== id);
    },
    updateTask(id) {
      console.log("task", id);
      this.tasks = this.tasks.map((task) =>
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    },
  },
};
</script>
