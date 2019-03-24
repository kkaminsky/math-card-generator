<template>
  <math-card></math-card>
</template>

<script>
import MathCard from './components/MathCard.vue'

export default {
  name: 'app',
  components: {
    MathCard
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
