<template>
  <div class="">
      <h1>Welcome to Quizzard!</h1>
      <players-name :playersName='name'></players-name>
      <categories-list :categories='categories'></categories-list>
      <category-question :categoryQuestions='categoryQuestions'></category-question>
  </div>
</template>

<script>
import CategoriesList from './components/CategoriesList.vue';
import CategoryQuestions from './components/CategoryQuestions.vue';
import Name from './components/Name.vue';
import {eventBus} from './main.js';
export default {
  data(){
    return {
      questions: [],
      categories: [],
      categoryQuestions: [],
      name: null
    }
  },
  methods: {
  },
  components: {
    "categories-list": CategoriesList,
    "category-question": CategoryQuestions,
    "players-name": Name
  },
  mounted(){
    fetch('https://opentdb.com/api.php?amount=100')
    .then(res => res.json())
    .then(questions => this.questions = questions.results)
    .then(() => { this.categories = [... new Set (this.questions.map(question => question.category))]
    // .split(': ')[0]
    })

    eventBus.$on('clicked-category', (category) => {
      this.categoryQuestions = this.questions.filter(question => category === question.category);
    })
    }
  }
</script>

<style>

</style>
