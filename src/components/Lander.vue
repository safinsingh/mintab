<template>
  <div class="main">
    <div class="time">
      <h2 v-text="hours"></h2>
      <h2 v-text="minutes"></h2>
      <h2 v-text="seconds"></h2>
    </div>
    <p>Made with <img src="../assets/logo.png"> by Safin Singh</p>
  </div>
</template>

<script>

import { getZeroPad } from './Filter'

export default {
  data () {
    return {
      hours: 0,
      minutes: 0,
      seconds: 0
    }
  },
  mounted () {
    this.$options.interval = setInterval(this.updateDateTime, 1000);
  },
  beforeDestroy () {
    clearInterval(this.$options.interval);
  },
  methods: {
    updateDateTime () {
      let now = new Date()
      this.hours = getZeroPad(now.getHours())
      this.minutes = getZeroPad(now.getMinutes())
      this.seconds = getZeroPad(now.getSeconds())
    }
  },
  name: 'Lander',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap');

h2, p {
  font-family: "Inter", "sans-serif";
}

p {
  position: fixed;
  bottom: 0;
  left: 50%;
  -webkit-transform: translateX(-50%);
  transform: translateX(-50%);
  font-weight: 400;
}

.main {
  min-height: 90%;
  min-height: 90vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.time h2 {
  font-weight: 700;
  font-size: 8rem;
  margin: 0.5rem 0rem;
}

img {
  height: 1em;
}
</style>
