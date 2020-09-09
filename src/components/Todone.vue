<template>
  <div class="todo-item" v-bind:class="{ isComplete: todo.isCompleted }">
    <input
      type="checkbox"
      :checked="todo.isCompleted"
      v-on:change="markComplete(todo.id)"
    />
    <label>{{ todo.content }}</label>
    <button class="delete" @click="$emit('del-todo', todo.id)">➖</button>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.isCompleted = !this.todo.isCompleted;
    },
  },
};
</script>
<style>
.isComplete {
  text-decoration: line-through;
}
</style>
