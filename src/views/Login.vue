<template>
   <h1>Login</h1>
   <button @click="handleLogin">Login</button>
</template>

<script>
export default {
   name: "Login",
   methods: {
      handleLogin() {
         this.$router.push({ name: "Home", params: { username: "Aamir" } });
      },
   },
};
</script>
