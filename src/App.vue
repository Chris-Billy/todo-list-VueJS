<template>
  <div id="app">
    <Horloge />
    <br>
    <TodoList />
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";
import Horloge from "./components/Horloge.vue"

export default {
  name: "App",
  components: {
    TodoList,
    Horloge
  },
  
  data() {
    return {
      task: ''
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
