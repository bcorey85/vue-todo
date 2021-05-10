<template>
  <div class="alert alert-danger" role="alert" v-if="error">
    {{ error }}
  </div>
</template>

<script>
export default {
  name: "todo-error",
  props: ["error"]
};
</script>

<style scoped>
</style>