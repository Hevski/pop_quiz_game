<template lang="html">
  <div @submit.prevent="onSubmit">
    <p>Enter players name:</p>
    <input v-model="name" type="text" value="">
    <button v-on:click="submitName">Add name</button>
    <h1>{{msg}}</h1>
  </div>
</template>

<script>
import {eventBus} from '../main.js';
export default {
  data(){
    return {
      name: null,
      msg: null
    }
  },
  methods: {
    submitName() {
      this.msg = "You're a Quizzard " + this.name + "!";
    }
   }
  }
</script>

<style lang="css" scoped>

h1 {
  font-family: 'Aclonica', sans-serif;
}
</style>
