<template>
  <div class="note">
    <h2>{{ note.title }}</h2>
    <p>{{ note.text }}</p>
    <button @click="editNote">Edit</button>
    <button @click="deleteNote">Delete</button>
  </div>
</template>

<script>
export default {
  props: ['note'],
  methods: {
    editNote() {
      this.$emit('edit', this.note);
    },
    deleteNote() {
      this.$emit('delete', this.note.id);
    },
  },
};
</script>

<style scoped>
.note {
  border: 1px solid #ccc;
  padding: 10px;
  margin-bottom: 10px;
}
</style>