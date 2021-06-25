<template>
   <QuizWrapper :quizzes="quizzes[this.currQuiz]" />
</template>

<script>
import QuizWrapper from "./components/QuizWrapper.vue";
import questions from "./assets/questions.json";

function changeQuestion() {
   this.currQuiz = this.currQuiz + 1;
}

export default {
   name: "App",
   components: {
      QuizWrapper,
   },
   data() {
      return {
         currQuiz: 0,
         quizzes: questions,
         onChange: changeQuestion,
      };
   },
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
</style>
