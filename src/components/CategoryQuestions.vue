<template lang="html">
  <div v-if="categoryQuestions">
    <h1>{{categotyQuestion.category}}</h1>
      <p>Difficulty: {{question.difficulty}}</p>
      <p>Question: {{question.question}}</p>
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
    }
  }
</script>

<style lang="css" scoped>
</style>
