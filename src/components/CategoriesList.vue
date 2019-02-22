<template lang="html">
  <div class="">
  <select v-on:change="handleChange" v-model="SelectedCategory">
    <option disable value=''>Select a category...</option>
    <option v-for="category in categories" :value="category" >{{category}}</option>
  </select>
</div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'categories-list',
  data (){
    return {
      SelectedCategory: '',
      questions: []
    }
  },
  props: ['categories'],
  methods: {
    handleChange(){
      eventBus.$emit('clicked-category', this.SelectedCategory)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
