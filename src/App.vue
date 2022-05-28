<template>
  <div>
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="!email">
      <login-form @login="logMeIn($event)"></login-form>
      <login-form @login="logMeIn($event)" button-label="Wejdź"></login-form>
      <login-form @login="logMeIn($event)" button-label="Wleć"></login-form>
      <login-form @login="logMeIn($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>
    </div>
    <div v-if="email">
      <logged-in-dashboard @logout="logout()" :email="email"></logged-in-dashboard>
    </div>

  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
import LoggedInDashboard from "@/LoggedInDashboard";
export default {
  components: {LoggedInDashboard, LoginForm},
  data() {
    return {
      email: ''
    };
  },
  methods: {
    logout() {
      this.email = '';
    },
    logMeIn(username) {
      this.email = username;
    }
  }
}
</script>

<style>
</style>
