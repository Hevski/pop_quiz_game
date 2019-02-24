<template lang="html">
  <GChart
    :type="chartType"
    :data='questions'
    :options="chartOptions"
  />
</template>

<script>
import { GChart } from 'vue-google-charts'
export default {
  name: 'graph',
  props: ['questions'],
  components: {
     "GChart": GChart
   }
}
</script>

<style lang="css" scoped>
</style>

<!-- v-if="chartData"
:type="chartType"
:data="chartData"
:options="chartOptions" -->
