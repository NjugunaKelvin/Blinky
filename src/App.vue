<template>
  <h1>Blinky</h1>
  <p>Let's Test Your Reflexes</p>
  <button @click="start" :disabled="isPlaying">Play</button>
  <p>Reaction Time: {{ score }}ms</p>
  <Block v-if="isPlaying" :delay="delay" @endgame="endGame"/>
</template>

<script>
import Block from './components/Block.vue'
export default {
  name: 'App',
  components: { Block },
  data(){
    return {
      isPlaying: false,
      delay: null,
      score: null
    }
  },
  methods: {
    start(){
      this.delay = 2000 + Math.random()*5000
      this.isPlaying = true
      // console.log(this.delay);
    },
    endGame(reactionTime){
      this.score = reactionTime
      this.isPlaying = false
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
