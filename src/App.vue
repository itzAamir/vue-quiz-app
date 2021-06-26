<template>
   <div class="container">
      <Score
         v-if="this.isFinished"
         :quizLength="this.quizLength"
         :score="this.score"
         @handle-retry="handleRetry"
      />
      <QuizWrapper
         :quizzes="quizzes[this.currQuiz]"
         @handle-next="handleNext"
         :currQuiz="this.currQuiz"
         :quizLength="this.quizLength"
         v-else
      />
   </div>
</template>

<script>
import QuizWrapper from "./components/QuizWrapper.vue";
import Score from "./components/Score.vue";
import questions from "./assets/questions.json";

export default {
   name: "App",
   components: {
      QuizWrapper,
      Score,
   },
   data() {
      return {
         currQuiz: 0,
         score: 0,
         quizLength: 0,
         quizzes: questions,
         isFinished: false,
      };
   },
   created() {
      this.quizLength = this.quizzes.length;
   },
   methods: {
      handleNext(option, answer) {
         if (option === answer) {
            this.score = this.score + 1;
         }

         if (this.currQuiz < this.quizzes.length - 1) {
            this.currQuiz = this.currQuiz + 1;
         } else {
            this.isFinished = true;
         }
      },
      handleRetry() {
         this.currQuiz = 0;
         this.score = 0;
         this.isFinished = false;
      },
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

.container {
   background: #3f4964;
   width: 40em;
   height: 18em;
   border-radius: 20px;
   padding: 2em;
}
</style>
