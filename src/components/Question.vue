<template lang="html">
  <div class="each-q">
    <p>Difficulty: {{question.difficulty}}</p>
    <p>Question: {{question.question}}</p>
    <div v-for="(answer, index) in question.incorrect_answers"class="">
      <p>{{answer}}</p>
      <div class="answers">
        <input type="radio" v-model="selectedAnswer" name="answer + index" v-bind:value="answer">
      </div>
    </div>
    <div class="button">
      <button v-on:click="handleClick">Answer</button>
      <!-- v-if="!isHidden" -->
      <!-- :disabled="handleClick" -->
      <h3>{{message}}</h3>
    </div>
  </div>
</template>

<script>
import {eventBus} from '../main.js'
export default {
  props: ['question'],
  data () {
    return {
      selectedAnswer: '',
      message: '',
      isHidden: false,
      score: 0,
    }
  },
  methods: {
    handleClick() {
    if (this.question.correct_answer === this.selectedAnswer) {
      this.isHidden = true
      this.increaseScore()
      eventBus.$emit('increase-score', this.score)
      this.message = "Your answer is correct!";
    } else {
      this.message = "Wrong answer! You need more quizzarding practice!";
      this.score = 0
    }
  },
  increaseScore() {
    this.score = 1
    // console.log(this.score);
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
  background: #baffba;
  flex-wrap: wrap;
  padding: 20px;
  text-align: -webkit-center;
  opacity: 0.9;
  font-family: 'Merriweather Sans', sans-serif;
  font-weight: bold;
  font-size: 20px;
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
