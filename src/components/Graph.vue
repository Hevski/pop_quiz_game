<template lang="html">
  <GChart
    :type="ColumnChart"
    :data='chartData'
    :options="chartOptions"
  />
</template>

<script>
import { GChart } from 'vue-google-charts'
export default {
  name: 'graph',
  props: ['graph', 'chartData', 'chartOptions'],
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
