<template lang="html">
  <div class="each-q">
    <p>Difficulty: {{question.difficulty}}</p>
    <p>Question: {{question.question}}</p>
    <div v-for="(answer, index) in question.incorrect_answers.sort()"class="">
      <p>{{answer}}</p>
      <div class="answers">
        <input type="radio" v-model="selectedAnswer" name="answer + index" v-bind:value="answer">
      </div>
    </div>
    <div class="button">
      <button v-on:click="handleClick">Answer</button>
      <h3>{{message}}</h3>
    </div>
  </div>
</template>

<script>
import categoryQuestions from './CategoryQuestions.vue';
export default {
  props: ['question'],
  data () {
    return {
      selectedAnswer: '',
      message: ''
    }
  },
  methods: {
    handleClick() {
    if (this.question.correct_answer === this.selectedAnswer) {
      this.message = "Your answer is correct!";
    }else{
      this.message = "Wrong answer! You need more quizzarding practice!";
    }
    }
  }
}
</script>

<style lang="css" scoped>

.each-q {
  display: flex;
  flex-direction: column;
  border-style: solid;
  padding: 12px;
  margin: 3px;
  width: 400px;
  height: auto;
  border-radius: 10px;
  background: #baffba;;
  flex-wrap: wrap;
  padding: 20px;
  text-align: -webkit-center;
  opacity: 0.9;
  font-family: 'Merriweather Sans', sans-serif;
  font-weight: bold;
}

.answers {
  background: #baffba;
}

p {
  background: #baffba;
  margin: 0;
  padding: 6px;
}

.button {
  background: #baffba;
}
</style>
