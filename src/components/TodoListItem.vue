<template>
  <div>
    <span>{{ task.task }}</span>
    <button @click="deleteTask">Supprimer</button>
    <button @click="task.done = !task.done">Done</button>
  </div>
</template>

<script>
export default {
  name: "TodoListItem",
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
button {
  margin-left: 10px
}
</style>
