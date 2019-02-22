<template lang="html">
  <div v-if="question">
    <h1>{{question.category}}</h1>
      <p>Difficulty: {{question.difficulty}}</p>
      <p>Question: {{question.question}}</p>
  </div>
</template>

<script>
export default {
  name: 'category-questions',
  props: ['question'],
  data () {
    return {
      categoryQuestions: []
    }
  },
  methods: {
    }
  }
</script>

<style lang="css" scoped>
</style>
