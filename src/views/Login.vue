<template>
   <div class="login-container">
      <h1 style="text-align:center">Sign In</h1>
      <form @submit="handleLogin(username)">
         <label for="username">Username: </label>
         <input v-model="username" type="text" id="username" />
         <label for="email">Email: </label>
         <input type="email" id="email" />
         <button type="submit">Login</button>
      </form>
   </div>
</template>

<script>
export default {
   name: "Login",
   data() {
      return {
         username: "",
      };
   },
   methods: {
      handleLogin(username) {
         this.$router.push({ name: "Home", params: { username: username } });
      },
   },
};
</script>

<style scoped>
.login-container {
   height: 20rem;
   width: 20rem;
   background: #3f4964;
   padding: 1rem;
   border-radius: 10px;
}

form {
   display: flex;
   flex-direction: column;
   margin-top: 2rem;
}

form input {
   margin-bottom: 1rem;
   font-size: 1rem;
   padding: 0.4rem;
   outline: none;
}

button {
   margin-top: 1rem;
   padding: 0.4rem 1rem;
   font-size: 1rem;
   color: white;
   background: #bb96c6;
   border: 2px solid;
   cursor: pointer;
   border-radius: 5px;
   transition: all ease 250ms;
}

button:hover {
   background-color: #3f4964;
   border: 2px solid #bb96c6;
}
</style>
