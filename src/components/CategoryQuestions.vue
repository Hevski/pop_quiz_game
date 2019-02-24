<template lang="html">
  <div class="question">
    <question v-for="(question, index) in categoryQuestions" :question="question" :key="index" />
  </div>
</template>

<script>
import Question from './Question.vue';
export default {
  name: 'category-questions',
  props: ['categoryQuestions', 'question'],
  data () {
    return {
    }
  },
   components: {
     "question": Question
   }
  }
</script>

<style lang="css" scoped>

.question {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  font-family: 'Aclonica', sans-serif;
  padding: 10px;
}
</style>
