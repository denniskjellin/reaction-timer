<template>
<h1>Vue 3 Reaction Timer</h1>
<button @click="start" :disabled="isPlaying">play</button>
<BlockComponent v-if="isPlaying" :delay="delay" />
</template>

<script>
import BlockComponent from './components/BlockComponent.vue'

export default {
  name: 'App',
  components: {
    BlockComponent,
  },
  data() {
    return {
      isPlaying: false,
      delay: null
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
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
