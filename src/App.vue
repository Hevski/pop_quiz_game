<template>
  <div class="">
      <h1>Quizzard!</h1>
      <categories-list :categories='categories'></categories-list>
  </div>
</template>

<script>
import CategoriesList from './components/CategoriesList.vue';
import CategoryQuestions from './components/CategoryQuestions.vue';
import {eventBus} from './main.js';
export default {
  data(){
    return {
      questions: [],
      categories: [],
      CategoryQuestions: []
    }
  },
  components: {
    "categories-list": CategoriesList
  },
  mounted(){
    fetch('https://opentdb.com/api.php?amount=100')
    .then(res => res.json())
    .then(questions => this.questions = questions.results)
    .then(() => { this.categories = [... new Set (this.questions.map(question => question.category))]
    // .split(': ')[0]
    })

    eventBus.$on('clicked-category', (category) => {
      this.CategoryQuestions = this.questions.filter(question => category === question.category)
    })
    eventBus.$on('category-questions', (questions) => {
      this.CategoryQuestions = questions
    })
  }
}
</script>

<style>

</style>
