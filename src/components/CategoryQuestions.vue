<template lang="html">
  <div class="question">
    <div v-for="(question, index) in categoryQuestions">
      <div class="each-q">
        <p>Difficulty: {{question.difficulty}}</p>
        <p>Question: {{question.question}}</p>
        <div v-for="answer in question.incorrect_answers"class="">
          <p>{{answer}}</p>
          <div class="answers">
            <input type="radio" name="answer" value="answer">
          </div>
        </div>
        <button @click="submitAnswer">Answer</button>
        <!-- <h3 v-if="answer === question.correct_answer">Correct!</h3>
        <h3 v-else="answer !== question.correct_answer">You need more quizzarding practice</h3> -->
      </div>
        <!-- <button type="button" v-on:click="answer === question.correct_answer">Correct!</button> -->
    </div>
  </div>

</template>

<script>
export default {
  name: 'category-questions',
  props: ['categoryQuestions'],
  data () {
    return {
      // selectedAnswer: ''
    }
  },
  methods: {
    submitAnswer(){
      // selectedAnswer =
    }
   },
  }
</script>

<style lang="css" scoped>

.question {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  font-family: 'Aclonica', sans-serif;
  padding: 10px;
}

.each-q {
  display: flex;
  flex-direction: column;
  border-style: solid;
  padding: 12px;
  margin: 3px;
  width: 400px;
  height: 300px;
  border-radius: 10px;
  background: beige;
  flex-wrap: wrap;
  padding: 20px;
}

p {
  background: beige;
  margin: 0;
  padding: 2px;
}

.answers {
  background: beige;
}
</style>
