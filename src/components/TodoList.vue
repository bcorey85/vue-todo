<template>
  <div>
    <ul v-for="todo in todos" :key="todo.todo" class="list-group">
      <Todo :todo="todo" @remove-todo="$emit('remove-todo', todo)" />
    </ul>
  </div>
</template>

<script>
import Todo from "./Todo";

export default {
  name: "TodoList",
  components: { Todo },
  props: ["todos"]
};
</script>


<style></style>