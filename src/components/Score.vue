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
</style>
