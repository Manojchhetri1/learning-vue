<template>
  <div>
    <h1>Register</h1>
    <form @submit.prevent="handleSubmit">
      <label for="name">Name:</label>
      <input type="text" id="name" v-model="name" required>
      <br><br>
      <label for="email">Email:</label>
      <input type="email" id="email" v-model="email" required>
      <br><br>
      <label for="password">Password:</label>
      <input type="password" id="password" v-model="password" required>
      <br><br>
      <button type="submit">Register</button>
    </form>
  </div>
</template>

<script>
// import frontendLayout from "@/layouts/frontend.vue";

export default {
  name: "App",
  // components: {
  //   frontendLayout,
  // },
  data() {
    return {
      name: '',
      email: '',
      password: ''
    }
  },
  methods: {
    handleSubmit() {
      // Here you can send a request to your server to register the user
      console.log('Name:', this.name)
      console.log('Email:', this.email)
      console.log('Password:', this.password)
      // After the registration is successful, you can redirect the user to another page
    }
  }
}
</script>
