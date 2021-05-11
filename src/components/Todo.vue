<template>
  <li
    class="mb-2 row d-flex align-items-center border p-2"
    :class="{ checked: checked }"
  >
    <input type="checkbox" class="mr-2" @click="toggleChecked" />
    <div class="flex-fill">{{ todo.todo }}</div>
    <div class="date">{{ localDate }}</div>
    <div class="pl-3">
      <button @click="$emit('remove-todo', todo)" class="btn btn-sm btn-danger">
        &times;
      </button>
    </div>
  </li>
</template>

<script>
export default {
  name: "Todo",
  props: ["todo"],
  data: function() {
    return {
      checked: false
    };
  },
  methods: {
    toggleChecked() {
      this.checked = !this.checked;
    }
  },
  computed: {
    localDate() {
      return new Date(this.todo.date).toLocaleString("en-US");
    }
  }
};
</script>

<style scoped>
.checked {
  text-decoration: line-through;
  color: #747474;
  background-color: #eee;
}

.date {
  text-align: right;
  min-width: 200px;
}
</style>