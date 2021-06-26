<template>
   <div class="quiz-container">
      <div class="question-wrapper">
         <span class="title"
            >Question {{ currQuiz + 1
            }}<span style="font-size: 0.7em">/{{ quizLength }}</span></span
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
               @handle-next="$emit('handle-next', option, quizzes.answer)"
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
      quizLength: Number,
      currQuiz: Number,
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
   height: 100%;
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
