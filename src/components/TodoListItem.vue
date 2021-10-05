<template>
  <div>
    <span>{{ task.task }}</span>
    <button @click="deleteTask">Supprimer<i class="fa fa-minus-circle" aria-hidden="true"></i></button>
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
