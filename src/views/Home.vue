<template>
  <div class="home">
    <app-login></app-login>
  </div>
</template>

<script>
// @ is an alias to /src
import AppLogin from "@/components/AppLogin.vue";

export default {
  name: "Home",
  components: {
    AppLogin
  }
};
</script>
