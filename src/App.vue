<template>
  <div id="app">
    <div class="container">
      <h1 class="text-center my-5">Vue Todo</h1>
      <TodoForm @add-todo="addTodo"></TodoForm>
      <todo-error :error="error"></todo-error>
      <TodoSort @sort-list="sortTodo"></TodoSort>
      <TodoList :todos="todos" @remove-todo="removeTodo"></TodoList>
    </div>
  </div>
</template>

<script>
import TodoList from "./components/TodoList";
import TodoForm from "./components/TodoForm";
import TodoSort from "./components/TodoSort";
import TodoError from "./components/TodoError";

export default {
  name: "App",
  components: { TodoList, TodoForm, TodoSort, TodoError },
  data: function() {
    return {
      todos: [],
      error: null
    };
  },
  methods: {
    addTodo(todo) {
      const isUnique =
        this.todos.filter(t => {
          return t.todo === todo;
        }).length === 0;

      if (todo && isUnique) {
        this.todos.push({
          todo,
          date: Date.now()
        });

        this.error = null;
      } else if (!isUnique) {
        this.error = "Todo already exists";
      } else {
        this.error = "Please add an item";
      }
    },
    removeTodo(todo) {
      this.todos = this.todos.filter(t => {
        return t !== todo;
      });
    },
    sortTodo(dir) {
      if (dir === "asc") {
        this.todos = this.todos.sort();
      } else {
        this.todos = this.todos.sort().reverse();
      }
    }
  }
};
</script>

<style scoped>
</style>
