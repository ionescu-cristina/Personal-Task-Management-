<template>
  <div class="home">
    <div>
      <h1>All task</h1>
      <ul>
        <li v-for="task in tasks" :key="task.id">
          {{ task.title }}
        </li>
      </ul>
    </div>

    <div>
      <input type="text" v-model="newTask"/>
      <button @click="addTask">Add new task</button>
    </div>
  </div>
</template>

<script>
let id = 0;
export default {
  name: "Home",
  components: {},
  data() {
    return {
      newTask: "",
      tasks: [
        { id: id++, title: "Learn Vue", done: true },
        { id: id++, title: "Learn CSS", done: true },
        { id: id++, title: "Learn HTML", done: true },
      ],
    };
  },
  methods: {
    addTask() {
      this.tasks.push({id: id++, title: this.newTask, done: false});
      this.newTask = ''
    },
  },
};
</script>
