<template>

  <div id="app-todolist">
    <a href="https://github.com/Rod1GitHub/Desafio2ToDoListVueJS" target="_blank">Link to git</a>
    <h1>Tareas para esta semana</h1>
    <div>
      <h2>Ingresar tarea:</h2>
      <input id="task" type="text" v-model="task"/>
      <button @click="addTaskMethod">Agregar a lista</button>
    </div>
    <div>
      <h2>Lista de tareas por hacer:</h2>
      <ul>
        <li v-for="(task, i) in tasks" :key="i">
          {{ getTaskMethod(i+1, task ) }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      task: "",
      tasks: [],
    };
  },
  methods: {
    getTaskMethod(index, task) {
      return `${index}: ${task}`;
    },
    addTaskMethod() {
      let { task } = this;
      this.tasks.push(task);
    },
  },
};
</script>

<style>
#app-todolist {
  font-family: Arial;
}
</style>