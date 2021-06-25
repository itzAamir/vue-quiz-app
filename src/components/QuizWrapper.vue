<template>
   <div class="quiz-container">
      <div class="question-wrapper">
         <span class="title"
            >Question 1<span style="font-size: 0.7em">/4</span></span
         >
         <br />
         <span class="question">{{ quizzes.question }}</span>
      </div>
      <div class="options-wrapper">
         <div class="option-container">
            <Option
               v-for="option of quizzes.options"
               :option="option"
               :key="option"
               :answer="quizzes.answer"
               :onChange="onChange"
            />
         </div>
      </div>
   </div>
</template>

<script>
import Option from "./Option.vue";

export default {
   name: "QuizWrapper",
   props: {
      quizzes: Object,
      onChange: Function,
   },
   components: {
      Option,
   },
};
</script>

<style scoped>
.quiz-container {
   display: grid;
   gap: 1rem;
   grid-template-columns: 1fr 1fr;
   background: #3f4964;
   width: 40em;
   height: 18em;
   border-radius: 20px;
   padding: 2em;
}

.title {
   font-size: 2em;
}

.question {
   display: inline-block;
   margin-top: 2rem;
   font-size: 1.3em;
}

.option-container {
   display: flex;
   flex-direction: column;
   justify-content: space-between;
   align-items: center;
   height: 100%;
}
</style>
