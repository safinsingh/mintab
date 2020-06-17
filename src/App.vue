<template>
  <div id="app">
    <Lander />
  </div>
</template>

<script>
import Lander from './components/Lander.vue'

export default {
  name: 'App',
  components: {
    Lander
  }
}
</script>

<style>
html, body {
  background-color: #0e0e0e;
}
#app {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(253, 253, 249);
}
</style>
