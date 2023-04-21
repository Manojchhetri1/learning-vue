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
    <HomeComponent data="Hello from home component" msg="It is a properties test"/>
    <WelcomeComponent />
    <h1>{{ title }}</h1>
    <childParent v-on:changeText="updateText($event)" />
  </div>
</template>

<script>
import HomeComponent from './components/HomeComponent.vue';
import WelcomeComponent from './components/WelcomeComponent.vue';
import childParent from './components/childParent.vue';

export default {
  name: "App",
  components: {
    HomeComponent,
    WelcomeComponent,
    childParent,
  },
  data() {
    return {
      name: '',
      email: '',
      password: '',
      title: "Data is proccessing"
    }
  },
  
  methods: {
    handleSubmit() {
      // Here you can send a request to your server to register the user
      console.log('Name:', this.name)
      console.log('Email:', this.email)
      console.log('Password:', this.password)
      // After the registration is successful, you can redirect the user to another page
    },
    updateText(title){
      this.title=title
},
  }
}
</script>
