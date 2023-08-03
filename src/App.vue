<template>
  <div class="container">
    <h1>Reaction Timer</h1>
    <button @click="startGame" :disabled="isPlaying">Play!</button>
    <Block v-if="isPlaying" :delay="delay"/>
  </div>
</template>

<script>
import Block from './components/Block.vue'
export default {
  components: {
    Block
  },
  data() {
    return {
      isPlaying: false,
      delay: null
    }
  },
  methods: {
    startGame() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
    }
  }
}
</script>

<style scoped>
.container {
  text-align: center;
}
</style>
