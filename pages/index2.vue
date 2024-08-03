<script setup>
const name = ref("John Doe");
const status = ref("active");
const tasks = ref(["Task One", "Task Two", "Task Three"]);
const newTask = ref("");

const toggleStatus = () => {
  if (status.value === "active") {
    status.value = "pending";
  } else if (status.value === "pending") {
    status.value = "active";
  }
};
const addTask = () => {
  if (newTask.value.trim() !== "") {
    tasks.value.push(newTask.value);
    newTask.value = "";
  }
};
const handleDelete = (index) => {
  tasks.value.splice(index, 1);
};

onMounted(async () => {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/todos");
    const data = await response.json();
    tasks.value = data.map((task) => task.title);
  } catch (error) {
    console.log("Error fetching tasks");
  }
});
</script>

<template>
  <div>this is home page</div>
  <p>Name :{{ name }}</p>
  <p>
    Status : <span class="tasks_style">{{ status }}</span>
  </p>
  <p v-if="status === 'pending'">User is pending.</p>
  <p v-if="status === 'active'">User is active.</p>

  <form @submit.prevent="addTask">
    <label for="newTask">Add Task</label>
    <input type="text" id="newTask" name="newTask" v-model="newTask" />
    <button type="submit">Submit</button>
  </form>
  <h3>Tasks:</h3>
  <ul v-for="(task, index) in tasks" :key="index">
    <li>
      <span>{{ task }}</span>
      <button @click="handleDelete(index)">x</button>
    </li>
  </ul>
  <button @click="toggleStatus">Click</button>
</template>

<style scoped>
.tasks_style {
  color: blue;
  text-transform: capitalize;
  font-size: xx-large;
}
</style>
