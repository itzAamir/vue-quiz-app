<template>
   <div class="score-container">
      <h1>{{ username }}, you've Scored {{ score }}/{{ quizLength }}</h1>
      <button @click="$emit('handle-retry')">Retry</button>
   </div>
</template>

<script>
export default {
   name: "Score",
   props: {
      quizLength: Number,
      score: Number,
      username: String,
   },
};
</script>

<style scoped>
.score-container {
   display: flex;
   flex-direction: column;
   justify-content: center;
   align-items: center;
   height: 100%;
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
