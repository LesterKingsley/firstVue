<template>
  <div>
    <h1>Add ToDo</h1>
    <form @submit="addNewTodo">
      <input v-model="content" name="content" />
      <button type="submit">add</button>
    </form>
  </div>
</template>

<script>
import { v4 as uuidv4 } from "uuid";
export default {
  name: "AddTodo",
  data() {
    return {
      content: "",
    };
  },
  methods: {
    addNewTodo(e) {
      e.preventDefault();
      let data = this.content;
      const newData = {
        id: uuidv4(),
        content: data,
        isCompleted: false,
      };
      this.$emit("add-todo", newData);
      this.content = "";
    },
  },
};
</script>
