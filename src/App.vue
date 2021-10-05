<template>
  <div id="app">
    <Horloge id="horloge" />
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
#horloge {
  font-size: 35px
}
</style>
