<template lang="html">
  <div @submit.prevent="onSubmit">
    <div class="header">
      <h1>{{title}}{{msg}}</h1>
      <p class="name">Enter players name:</p>
      <div class="name-input">
        <input class="input" v-model="name" type="text" value="">
        <button class="name-button"v-on:click="submitName">Add name</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      name: null,
      msg: null,
      title: "Welcome to Quizzard"
    }
  },
  methods: {
    submitName() {
      this.msg = "You're a Quizzard " + this.name + "!";
      this.title = ''
    }
  },
  }
</script>

<style lang="css" scoped>

.header {
  font-family: 'Aclonica', sans-serif;
  text-align: center;
  font-size: 40px;
  border-style: solid;
  background: #c1ffc1;
  opacity: 0.8;
  border-radius: 9px;
  align-items: center;
}

h1 {
  margin: 16px;
}

.name {
  font-family: 'Aclonica', sans-serif;
  text-align: center;
  font-size: 30px;
  margin: 2px;
}

.name-input {
  display: flex;
  justify-content: center;
  margin: 10px;
}

.name-button {
  font-size: 18px;
  margin: 5px;
}

.input {
  font-size: 20px;
}
</style>
