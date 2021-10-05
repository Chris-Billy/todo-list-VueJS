<template>
  <div>
    <span>{{ task.task }}</span>
    <button @click="deleteTask">Supprimer</button>
    <button @click="task.done = !task.done">UnDone</button>
  </div>
</template>

<script>
export default {
  name: "TodoListItemDone",
  props: {
    task: Object,
  },
  methods: {
    deleteTask: function() {
      this.$emit("delete");
    },
  },
};
</script>

<style scoped>
div {
  margin-bottom: 10px;
}
span {
  text-decoration: line-through;
}
button {
  margin-left: 10px
}
</style>
