<template>
   <div class="answer" @click="handleClick()">
      {{ option }}
   </div>
</template>

<script>
export default {
   name: "Option",
   props: {
      option: String,
   },
   methods: {
      handleClick() {
         this.$emit("handle-next", this.option);
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
