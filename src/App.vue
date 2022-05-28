<template>
  <div>
<!--    <h1>Twój e-mail to {{ email }}</h1>-->
<!--    <div v-if="email.length < 10">Ale masz krótki adres!</div>-->
<!--    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>-->
<!--    <div v-else class="red">Twój adres e-mail jest stanowczo za długi.</div>-->
<!--    <input @keyup.enter="alertMyEmail()" type="email" v-model="email">-->
<!--    <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button>-->
    <h1>Witaj w systemie do zapisów na zajęcia</h1>
    <span v-if="!loggedIn">Zaloguj się e-mailem</span>
    <input v-if="!loggedIn" type="text" v-model="email">
    <button v-if="!loggedIn" @click="login()">Wchodzę</button>
    <div v-if="loggedIn"><h2>Witaj {{ email }}!</h2></div>
    <div v-if="loggedIn"><h3><a href="#" @click="logout()">Wyloguj</a></h3></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      loggedIn: false
    };
  },
  methods: {
    // alertMyEmail() {
    //   alert(this.email);
    // },
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
.red {
  color: red;
}
a {
  text-decoration:none;
}
</style>
