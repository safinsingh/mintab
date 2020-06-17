<template>
  <div class="main">
    <div class="time">
      <h2 v-text="hours"></h2>
      <h2 v-text="minutes"></h2>
      <h2 v-text="seconds"></h2>
    </div>
    <p>
      Made with
      <a href="https://vuejs.org/">
        <img src="../assets/logo.png" />
      </a> by Safin Singh
      <a href="https://github.com/safinsingh/mintab">
        <img src="../assets/gh.svg" class="gh" />
      </a>
    </p>
  </div>
</template>

<script>
import { getZeroPad } from "./Filter";

export default {
  data() {
    return {
      hours: 0,
      minutes: 0,
      seconds: 0
    };
  },
  mounted() {
    this.$options.interval = setInterval(this.updateDateTime, 1000);
  },
  beforeDestroy() {
    clearInterval(this.$options.interval);
  },
  methods: {
    updateDateTime() {
      let now = new Date();
      this.hours = getZeroPad(now.getHours());
      this.minutes = getZeroPad(now.getMinutes());
      this.seconds = getZeroPad(now.getSeconds());
    }
  },
  name: "Lander"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h2,
p {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica,
    Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
  font-display: optional;
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
  font-size: 8em;
  margin: 0.5rem 0rem;
}

img {
  height: 1em;
  margin: 0rem 0.2em;
  -webkit-transform: translateY(0.19em);
  transform: translateY(0.19em);
  transition: all 0.3s;
}

img:hover {
  -webkit-transform: translateY(-0.19em);
  transform: translateY(-0.19em);
}
</style>
