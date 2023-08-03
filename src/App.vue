<template>
  <div class="container">
    <h1>Reaction Timer</h1>
    <button @click="startGame" :disabled="isPlaying">Play!</button>
    <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
    <Result v-if="score" :score="score"/>
  </div>
</template>

<script>
import Block from './components/Block.vue'
import Result from './components/Result.vue'
export default {
  components: {
    Block,
    Result
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null
    }
  },
  methods: {
    startGame() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.score = null
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
    }
  }
}
</script>

<style scoped>
.container {
  text-align: center;
}
</style>
