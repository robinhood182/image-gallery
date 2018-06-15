<template>
  <div>
    <h3>Sign up</h3>
    <form @submit.prevent="handleSubmit">
      <label>
        Username:
        <input v-model="user.username" type="text" required>
      </label>
      <label>
        Password:
        <input v-model="user.password" type="password" required>
      </label>
      <button type="submit">Sign Up</button>
    </form>
  </div>
</template>

<script>
import { addUser } from '../services/api';
export default {
  data() {
    return {
      user: {
        username: '',
        password: ''
      }
    };
  },
  methods: {
    handleSubmit() {
      return addUser(this.user)
        .catch(err => {
          this.error = err;
        })
        .then(saved => {
          if(saved) {
            this.$router.push('/albums/new');
          }
        });
    }
  }
};
</script>

<style>

</style>
