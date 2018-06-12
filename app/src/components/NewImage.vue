<template>
  <div>
    <h1>Add New Image</h1>
    <form @submit.prevent="handleSubmit">
      <input v-model="newImage.url" type="text" required>
      <input v-model="newImage.title" type="text" required>
      <textarea v-model="newImage.description"></textarea>
      <button type="submit">Add</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newImage: {
        url: '',
        title: '',
        description: ''
      }
    };
  },

  props: ['onAdd'],

  methods: {
    handleSubmit() {
      this.onAdd(this.newImage);
    }
  }
};
</script>

<style>

</style>

