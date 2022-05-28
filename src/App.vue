<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="!loggedIn">
      <span>Zaloguj się e-mailem</span>
      <input type="text" v-model="email">
      <button @click="login()">Wchodzę</button>
    </div>
    <div v-if="loggedIn">
      <h2>Witaj {{ email }}!</h2>
      <h3><a href="#" @click="logout()">Wyloguj</a></h3>
    </div>
  </div>
</template>

<script>
import "milligram";
export default {
  data() {
    return {
      email: '',
      loggedIn: false
    };
  },
  methods: {
    login() {
      this.loggedIn = true;
    },
    logout() {
      this.loggedIn = false;
      this.email = '';
    }
  }
}
</script>

<style>
</style>
