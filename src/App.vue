<template>
   <router-view></router-view>
</template>

<script>
export default {
   name: "App",
};
</script>

<style>
* {
   margin: 0;
   padding: 0;
}

body {
   font-family: Verdana, Geneva, Tahoma, sans-serif;
   background: #be93c5;
   background: linear-gradient(to left, #7bc6cc, #be93c5);
   color: white;
}

#app {
   height: 90vh;
   display: grid;
   place-items: center;
}

.container {
   background: #3f4964;
   width: 40em;
   height: 18em;
   border-radius: 20px;
   padding: 2em;
}
</style>
