<template>
  <div>
    <input
      id="saisie"
      v-model="task"
      type="text"
      placeholder="Entrez une tâche à ajouter"
    />
    <button id="ajouter" @click="addTask(task)">Ajouter <i class="fa fa-plus-circle" aria-hidden="true"></i></button>
    <br /><br />

    <div>Liste des taches :</div>
    <ul>
      <li v-for="(task, index) in todoList" :key="index" class="fadeIn">
        <TodoListItem
          v-if="!task.done"
          :task="task"
          @delete="deleteTask(index)"
        />
        <TodoListItemDone v-else :task="task" @delete="deleteTask(index)" />
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
      task: '',
      todoList: [
        {
          task: "test",
          done: false,
        },
      ],
    };
  },
  methods: {
    addTask: function(task) {
      this.todoList.push({
        task,
        done: false,
      });
      this.task = "";
    },
    deleteTask: function(index) {
      this.todoList.splice(index, 1);
    },
  },
};
</script>

<style>
li {
  list-style: none;
}
* {
  text-align: center;
  background-color: rgb(36, 36, 36);
  color: white;
  font-size: 20px;
}

#saisie {
  width: 35%;
  text-align: left;
  padding: 10px;
  padding-left: 20px;
  border-radius: 10px;
  border: 2px solid white;
}

button {
  padding: 10px;
  border-radius: 10px;
  margin: 15px;
  border: 2px solid white;
}

button:hover {
  cursor: pointer;
}

i {
  font-size: 25px !important;
  margin-left: 10px;
}

i:hover {
  cursor: pointer;
}

.fa-plus-circle {
  color: rgba(0, 255, 0, 0.685);
}

.fa-minus-circle {
  color: rgba(255, 0, 0, 0.733);
  margin-left: 15px;
}

#list {
  width: 50%;
  min-height: 60vh;
  margin: auto;
  margin-top: 15px;
  text-align: left;
  border-radius: 10px;
  border: 2px solid white;
}

h1 {
  padding-bottom: 20px;
  border-bottom: 2px solid white;
}

.fadeIn {
  animation: fadeIn ease 2s;
}

.fadeOut {
  animation: fadeOut ease 2s;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
@keyframes fadeOut {
  0% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}
</style>
