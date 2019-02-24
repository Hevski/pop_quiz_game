<template lang="html">
  <div class="score">
    <p>Your current score is {{totalScore}}</p>
  </div>
</template>

<script>
export default {
  name: 'score',
  props: ['totalScore'],
}
</script>

<style lang="css" scoped>

.score {
  display: flex;
  justify-content: center;
  font-family: 'Aclonica', sans-serif;
  font-size: 20px;
  border-style: solid;
  background: #baffba;
  border-radius: 10px;
  opacity: 0.8;
  border-style: solid;
  margin: 5px;
  /* position: fixed; */
}
</style>
