<template>
  <h1> hello jovic</h1>
  <button @click="start" >play</button>
  <Block v-if="isplaying" :disabled="isplaying" v-bind:delay="delay" @end="endGame" />
  <p v-if="showResults">Reaction time : {{ score }}</p>
</template>

<script>

import Block from './components/Block.vue'

export default {
  name: 'App',
  components: { Block},
  data() {
    return{
        isplaying : false,
        delay : null,
        score:null,
        showResults: false,
    }
  },
  methods:{
    start(){
      this.delay =2000 + Math.random() *5000 //so here we will get a radom number from 0 - 5000 mili secconds
      this.isplaying =!this.isplaying
    },
    endGame(time){
      this.score = time
      this.showResults =!this.showResults
      this.isplaying =false

    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
