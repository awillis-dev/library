<template>
  <div class="p-4 flex justify-center">
    <button class="btn" @click="toggleForm">
      <i class="material-icons mr-2 my-1">add</i>
      <span>Add Book</span>
    </button>
  </div>
</template>

<script>
export default {
  methods: {
    toggleForm() {
      // Emit the toggle event to the parent component
      this.$emit("toggle");
    },
  },
};
</script>

<style scoped></style>
