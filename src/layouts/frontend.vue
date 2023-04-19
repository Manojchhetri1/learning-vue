<template>
    <form @submit.prevent="login">
      <div>
        <label for="email">Email:</label>
        <input type="email" id="email" v-model="email" required>
      </div>
      <div>
        <label for="password">Password:</label>
        <input type="password" id="password" v-model="password" required>
      </div>
      <button type="submit">Login</button>
    </form>
  </template>
  
  <script>
  export default {
    name: "frontendLayout",
    data() {
      return {
        email: '',
        password: ''
      }
    },
    methods: {
      login() {
        // handle login logic here
      }
    }
  }
  </script>
  