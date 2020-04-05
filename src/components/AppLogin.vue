<template>
  <div class="login">
    <form @submit.prevent="logIn">
      <label for="">
        <input type="text" v-model="email" />
      </label>
      <label for="">
        <input type="password" v-model="password" />
      </label>
      <input type="submit" value="Login" />
    </form>
  </div>
</template>

<script>
import firebase from "firebase/app";
import "firebase/app";
import "firebase/auth";

export default {
  name: "app-login",
  data() {
    return {
      email: "",
      password: ""
    };
  },
  methods: {
    logIn() {
      firebase
        .auth()
        .signInWithEmailAndPassword(this.email, this.password)
        .then(() => {
          this.$router.replace("private");
        })
        .catch(function(error) {
          console.log(error.message);
        });
    }
  }
};
</script>
