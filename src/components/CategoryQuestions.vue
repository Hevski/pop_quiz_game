<template lang="html">
  <div class="">
    <div v-for="question in categoryQuestions">
        <p>Difficulty: {{question.difficulty}}</p>
        <p>Question: {{question.question}}</p>
        <div v-for="answer in question.incorrect_answers"class="">
        <p>{{answer}}</p>
        <input type="radio" name="answer" value="answer">
        </div>
    </div>
  </div>

</template>

<script>
export default {
  name: 'category-questions',
  props: ['categoryQuestions'],
  data () {
    return {
      answers: []
    }
  },
  methods: {
  },
  }
</script>

<style lang="css" scoped>
</style>
