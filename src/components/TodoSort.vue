<template>
  <div class="row justify-content-end mb-3">
    <button
      @click="$emit('sort-list', 'asc')"
      class="btn btn-sm btn-outline-secondary mr-2"
    >
      Asc
    </button>
    <button
      @click="$emit('sort-list', 'desc')"
      class="btn btn-sm btn-outline-secondary"
    >
      Desc
    </button>
  </div>
</template>

<script>
export default {
  name: "TodoSort"
};
</script>

<style></style>
