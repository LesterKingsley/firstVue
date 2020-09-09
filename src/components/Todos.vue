<template>
  <div>
    <h1>Todo</h1>

    <div v-bind:key="todo.id" v-for="todo in todos">
      <Todone v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
    </div>
  </div>
</template>

<script>
import Todone from "./Todone";
export default {
  name: "Todos",
  components: { Todone },
  props: ["todos"],
};
</script>
