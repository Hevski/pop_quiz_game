<template lang="html">
  <div class="select">
  <select class="select-category" v-on:change="handleChange" v-model="SelectedCategory">
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
      categoryQuestions: []
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

.select {
  display: flex;
  justify-content: center;
  font-size: 30px;
}

.select-category {
  font-size: 19px;
}

</style>
