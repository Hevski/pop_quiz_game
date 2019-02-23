<template lang="html">
  <div class="">
    <div v-for="question in categoryQuestions">
      <!-- <h1>{{question.category}}</h1> -->
        <p>Difficulty: {{question.difficulty}}</p>
        <p>Question: {{question.question}}</p>
    </div>
  </div>

</template>

<script>
export default {
  name: 'category-questions',
  props: ['categoryQuestions'],
  data () {
    return {
    }
  },
  methods: {
  },
  }
</script>

<style lang="css" scoped>
</style>
