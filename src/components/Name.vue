<template lang="html">
  <div @submit.prevent="onSubmit">
    <p class="name">Enter players name:</p>
    <div class="name-input">
      <input v-model="name" type="text" value="">
      <button v-on:click="submitName">Add name</button>
    </div>
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
  text-align: center;
  font-size: 50px;
}

.name {
  font-family: 'Aclonica', sans-serif;
  text-align: center;
  font-size: 20px;
}

.name-input {
  display: flex;
  justify-content: center;
}
</style>
