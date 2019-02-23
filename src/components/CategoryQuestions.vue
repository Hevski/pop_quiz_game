<template lang="html">
  <div class="">
    <div v-for="(question, index) in categoryQuestions">
      <!-- <div class="" v-show="index === questionIndex"> -->
        <p>Difficulty: {{question.difficulty}}</p>
        <p>Question: {{question.question}}</p>
        <div v-for="answer in question.incorrect_answers"class="">
          <p>{{answer}}</p>
          <input type="radio" name="answer" value="answer">
        </div>
        <!-- <button v-if="questionIndex > 0" v-on:click="prev">prev</button>
        <button v-on:click="next">next</button> -->
      <!-- </div> -->
    </div>
  </div>

</template>

<script>
export default {
  name: 'category-questions',
  props: ['categoryQuestions'],
  data () {
    return {
      answers: [],
      questionIndex: '',
      // next: ''
    }
  },
  methods: {
  },
  }
</script>

<style lang="css" scoped>
</style>
