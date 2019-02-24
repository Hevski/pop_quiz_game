<template>
  <div class="">
      <!-- <img src="./assets/wizard.png" alt="Italian Trulli"> -->
      <players-name :playersName='name'></players-name>
      <categories-list :categories='categories'></categories-list>
      <category-questions :categoryQuestions='categoryQuestions'></category-questions>
  </div>
</template>

<script>
import CategoriesList from './components/CategoriesList.vue';
import CategoryQuestions from './components/CategoryQuestions.vue';
import Name from './components/Name.vue';
import Question from './components/Question.vue';

import {eventBus} from './main.js';
export default {
  data(){
    return {
      questions: [],
      categories: [],
      categoryQuestions: [],
      name: null,
    }
  },
  methods: {
    formatQuestions: function(res){
      this.questions = this.questions.map(function(question){
        question.incorrect_answers.push(question.correct_answer)
        return question
      });
    }
  },
  components: {
    "categories-list": CategoriesList,
    "category-questions": CategoryQuestions,
    "players-name": Name,
  },
  mounted(){
    fetch('https://opentdb.com/api.php?amount=100')
    .then(res => res.json())
    .then(questions => this.questions = questions.results)
    .then((res) => {
      this.formatQuestions(res)
    })
    .then(() => { this.categories = [... new Set (this.questions.map(question => question.category))]
    })
    .then(()=> this.categories.unshift('All Categories'))

    eventBus.$on('clicked-category', (category) => {
      if (category === 'All Categories') {
        this.categoryQuestions = this.questions
      }
      else {
      this.categoryQuestions = this.questions.filter(question => category === question.category);
      }
    })
    }
  }
</script>

<style>

body {
  background: url('./assets/wizard.png') no-repeat fixed center;
  padding-top: 10px;
}

</style>
