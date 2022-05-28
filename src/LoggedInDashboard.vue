<template>
  <div>
    <h2>Witaj {{ email }}!</h2>
    <h3><a href="#" @click="logout()">Wyloguj</a></h3>
  </div>
</template>

<script>
export default {
  name: "LoggedInDashboard",
  props: ['email'],
  methods: {
    logout() {
      this.$emit("logout");
    }
  }
}
</script>

<style scoped>

</style>