<template>
  <HelloWorld msg="Welcome to Your Vue.js App" />
  <body class="sign-up-body">
    <section id="elzero-app" class="box">
      <form>
        <div class="icon">
          <img src="../assets/web.png" alt="">
        </div>
        <h2>Get Started today </h2>
        <p>Every novel has a writer .. There is no cheating in novels anymore</p>
        <div class="input-box">
          <label for="name">
          <input type="text" name="" v-model="name"  id="name" required>
          <span>Name</span>
          <i></i>
          </label>
        </div>
        <div class="input-box">
          <label for="password">
          <input type="password" name="" v-model="password" id="password" required>
          <span>Password</span>
          <i></i>
          </label>
        </div>
        <div class="input-box">
          <label for="email">
          <input type="email" name="" v-model="email" id="email" required>
          <span>E-mail</span>
          <i></i>
          </label>
        </div>
        <div class="input-box">
          <label for="age">
          <input type="number" name="" v-model="age" id="age" required min="18" max="60">
          <span>Age</span>
          <i></i>
          </label>
        </div>
        <input @click="signUp" type="submit" value="Register">
      </form>
    </section>
  </body>
</template>

<script>
import HelloWorld from '@/components/HelloWorld.vue';
import axios from 'axios';

export default {
  name: 'HomeView',
  data() {
    return {
      name: '',
      email: '',
      password: '',
      age: '',
    };
  },
  methods: {
    async signUp() {
      const user = {
        name: this.name,
        email: this.email,
        password: this.password,
        age: this.age,
      };

      try {
        const response = await axios.post('http://localhost:8888/user/addUser', user);
        console.log('User registered successfully!', response.data);
        alert('Sign up is done');
      } catch (error) {
        console.error('An error occurred during registration:', error);
      }
    },
  },
  components: {
    HelloWorld,
  },
};
</script>

<style src="../css/normalize.css"></style>
<style src="../css/main.css"></style>
