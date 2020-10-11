<template>
  <div>
    <form  @submit.prevent="login"  class="formulario">
      <h2>Login</h2>
      <input v-model="usuario" type="text" placeholder="Usuario" />
      <input v-model="contrasena" type="password" placeholder="Contraseña" />
      <input type="submit" value="ingresar" />
    </form>
 <h1>user:revanskyw@gmail.com</h1>
    <h1>pass:12345678</h1>

    <pre>

      {{$data}}
    </pre>
  </div>
</template>

<script>
import firebase from 'firebase'
export default {
  data() {
    return {
      usuario: "",
      contrasena: ""
    };
  },

  methods: {
    login() {
      firebase
        .auth()
        .signInWithEmailAndPassword(this.usuario, this.contrasena)
        .then((user) => this.$router.replace('home'),(error) => console.error(error));
        
    },
  },
};
</script>

<style lang="scss">
.formulario {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 5px;
}
</style>
