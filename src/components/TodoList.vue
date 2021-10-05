<template>
  <div>
    <input
      v-model="task"
      type="text"
      placeholder="Entrez une tache à ajouter"
    />
    <button @click="addTask(task)">Ajouter</button>
    <br /><br />
    
    <div>Liste des taches :</div>
    <ul>
      <li v-for="(task, index) in todoList" :key="index">
        <TodoListItem
          v-if="!task.done"
          :task="task"
          @delete="deleteTask(index)"
        />
        <TodoListItemDone
          v-else
          :task="task"
          @delete="deleteTask(index)"
        />
      </li>
    </ul>
  </div>
</template>

<script>
import TodoListItem from "./TodoListItem.vue";
import TodoListItemDone from "./TodoListItemDone.vue";

export default {
  name: "TodoList",
  components: {
    TodoListItem,
    TodoListItemDone,
  },
  data() {
    return {
      todoList: [
        {
          task: "test",
          done: false,
        },
      ],
    };
  },
  props: {
    task: String
  },
  methods: {
    addTask: function (task) {
      this.todoList.push({
        task,
        done: false,
      });
      this.task = "";
    },
    deleteTask: function (index) {
        this.todoList.splice(index, 1)
    }
  },
};
</script>

<style>
li {
  list-style: none;
}
</style>
