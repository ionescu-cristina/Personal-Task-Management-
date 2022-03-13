<template>
  <div class="home">
    <div class="flex">
      <div class="border">
        <h1>All tasks</h1>
        <ul>
          <li v-for="task in tasks" :key="task.id">
            <input type="checkbox" v-model="task.completed" />
            {{ task.title }}
            <button @click="removeTask(task)">X</button>
          </li>
        </ul>
      </div>

      <div class="border">
        <h1>Completed Tasks</h1>
        <ul>
          <li v-for="task in completedTasks" :key="task.id">
            {{ task.title }}
          </li>
        </ul>
      </div>

      <div class="border">
        <h1>Uncompleted Tasks</h1>
        <ul>
          <li v-for="task in uncompletedTasks" :key="task.id">
            {{ task.title }}
          </li>
        </ul>
      </div>
    </div>

    <div>
      <input type="text" v-model="newTask" />
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
        { id: id++, title: "Learn Vue", completed: true },
        { id: id++, title: "Learn CSS", completed: true },
        { id: id++, title: "Learn HTML", completed: false },
      ],
    };
  },
  methods: {
    addTask() {
      this.tasks.push({ id: id++, title: this.newTask, completed: false });
      this.newTask = "";
    },
    removeTask(task) {
      this.tasks = this.tasks.filter((t) => t !== task);
    },
  },
  computed: {
    completedTasks() {
      return this.tasks.filter((task) => task.completed);
    },
    uncompletedTasks() {
      return this.tasks.filter((task) => !task.completed);
    },
  },
};
</script>

<style>
.flex {
  display: flex;
  justify-content: center;

}
.flex > div {
  margin: 50px;
  padding: 50px;
}
.flex > div ul {
  text-align: justify;
  
}
.border {
    border: 1px solid 	#808080;
}
</style>
