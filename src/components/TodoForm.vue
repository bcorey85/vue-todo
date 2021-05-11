<template>
  <form @submit.prevent="addTodo" class="mb-4 row">
    <div class="input-group justify-content-center">
      <input id="add-todo" type="text" v-model="todoText" />
      <div class="input-group-append">
        <button type="submit" class="btn btn-success">Add</button>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  name: "TodoForm",
  components: {},
  data: function() {
    return {
      todoText: null
    };
  },
  methods: {
    addTodo(e) {
      this.$emit("add-todo", this.todoText);
      e.target.reset();
      this.todoText = "";
    }
  }
};
</script>


<style scoped>
</style>