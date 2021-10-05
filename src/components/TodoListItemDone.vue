<template>
  <div>
    <span>{{ task.task }}</span>
    <button @click="fadeOut">Supprimer<i class="fa fa-minus-circle" aria-hidden="true"></i></button>
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
    fadeOut() {
      this.$el.parentElement.classList.add("fadeOut");
      setTimeout(() => {
        this.deleteTask();
      }, 2000);
    },
  },
};
</script>

<style scoped>
span {
  text-decoration: line-through;
}
</style>
