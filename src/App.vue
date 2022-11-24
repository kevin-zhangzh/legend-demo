<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <OTC></OTC>
</template>

<script>
import OTC from './components/OTC.vue'

export default {
  name: 'App',
  components: {
    OTC
  }
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
