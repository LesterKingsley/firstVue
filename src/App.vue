<template>
  <div id="app">
    <div>
      <AddTodo v-on:add-todo="addTodo" />
      <Todos v-bind:todos="todolist" v-on:del-todo="deleteTodo" />
    </div>
  </div>
</template>
<script>
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";
export default {
  name: "App",
  components: {
    Todos,
    AddTodo,
  },
  data() {
    return {
      todolist: [
        { id: 1, content: "cook a meal", isCompleted: true },
        { id: 2, content: "water the plants", isCompleted: false },
        { id: 3, content: "shove the ice", isCompleted: true },
      ],
    };
  },
  methods: {
    deleteTodo(id) {
      this.todolist = this.todolist.filter((todo) => todo.id != id);
    },
    addTodo(newData) {
      console.log(newData);
      this.todolist = [...this.todolist, newData];
    },
  },
  created() {
    console.log("hey");
  },
};
</script>
