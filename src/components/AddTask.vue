<template>
  <form @submit="submitHandler">
    <label for="task">Add Task</label>
    <input type="text" name="task" v-model="taskName" />
    <label for="day">Day</label>
    <input type="text" name="day" v-model="dayName" />
    <button type="submit">Submit</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      taskName: "",
      dayName: "",
    };
  },
  methods: {
    submitHandler(e) {
      e.preventDefault();
      console.log(this.taskName, this.dayName);
      const newTask = {
        id: Math.floor(Math.random() * 10000),
        text: this.taskName,
        day: this.dayName,
        reminder: false,
      };
      this.$emit("add-task", newTask);
      this.taskName = "";
      this.dayName = "";
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
}
form button {
  width: 44%;
  padding: 0.5rem;
}
form input {
  width: 89%;
  padding: 0.5rem 0.4rem;
  border-radius: 0.4rem;
  border: none;
}
</style>
