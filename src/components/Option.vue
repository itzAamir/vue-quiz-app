<template>
   <div class="answer" @click="handleClick()">
      {{ option }}
   </div>
</template>

<script>
export default {
   name: "Option",
   props: ["option", "answer", "onChange"],
   methods: {
      handleClick() {
         if (this.option === this.answer) {
            console.log("correct");
            // this.onChange();
         }
         //  console.log("option -> ", this.option);
         //  console.log("answer -> ", this.answer);
      },
   },
};
</script>

<style scoped>
.answer {
   font-size: 1.2em;
   border: 4px solid #7fc3cc;
   width: 80%;
   padding: 0.6rem;
   border-radius: 15px;
   cursor: pointer;
   transition: all ease 250ms;
}

.answer:hover {
   background: #bc95c6;
}
</style>
