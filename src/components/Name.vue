<template lang="html">
  <div @submit.prevent="onSubmit">
    <p>Enter your name</p>
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
      this.msg = "Your a quizzard " + this.name + "!";
    }
   }
  }
</script>

<style lang="css" scoped>
</style>
