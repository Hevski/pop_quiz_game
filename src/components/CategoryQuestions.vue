<template lang="html">
  <div v-if="showQuestions()">
    <h1>{{question.category}}</h1>
      <p>Difficulty: {{question.difficulty}}</p>
      <p>Question: {{question.question}}</p>
  </div>
</template>

<script>
import {eventBus} from '../main.js'
export default {
  name: 'category-questions',
  props: ['CategoryQuestions'],
  data () {
    return {
      CategoryQuestions: []
    }
  },
  props: ['CategoryQuestions'],
  methods: {
    showQuestions(){
      eventBus.$emit('CategoryQuestions', this.CategoryQuestions)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
