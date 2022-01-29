<template>
  <div id="app-todolist">
    <a
      href="https://github.com/Rod1GitHub/Desafio2ToDoListVueJS"
      target="_blank"
      >Link to git</a
    >
    <h1>Tareas para esta semana</h1>
    <div>
      <h2>Ingresar tarea:</h2>
      <input id="idInputTask" type="text" v-model="taskSingularInput003" />
      <button @click="captureInputAndAddToEndOfArrayMethod003">
        Capturar y agregar al Array
      </button>
    </div>
    <div>
      <h2>Lista de tareas por hacer:</h2>
      <ul>
        <li
          v-for="(taskArgument003, index003) in tasksPluralArray003"
          :key="index003"
        >
          {{ printFromArrayToHtmlMethod003(index003 + 1, taskArgument003) }}
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
      taskSingularInput003: "",
      tasksPluralArray003: [],
    };
  },
  methods: {
    captureInputAndAddToEndOfArrayMethod003() {
      let { taskSingularInput003 } = this; // Esto captura el input
      this.tasksPluralArray003.push(taskSingularInput003); // push() lo envía al final del array
    },
    printFromArrayToHtmlMethod003(indexParam003, taskParam003) {
      return `${indexParam003}: ${taskParam003}`;
    },
  },
};
</script>

<style>
#app-todolist {
  font-family: Arial;
}
</style>
