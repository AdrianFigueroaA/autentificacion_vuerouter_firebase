<template>
  <div class="home">
    <h1>Hola soy el Home</h1>
    <button @click="logout">Cerrar Sesion</button>
  </div>
</template>

<script>
// @ is an alias to /src

import firebase from "firebase";
export default {
  name: "Home",

  methods: {
    logout() {
      firebase
        .auth()
        .singOut()
        .then(() => this.$router.replace('login'));
    },
  },
};
</script>
