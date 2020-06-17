<template>
  <div id="app">
    <custom-cursor
      :targets="['img', 'a', 'button']"
      :circleColor="'#fff'"
      :circleColorHover="'#fff'"
      :dotColor="'#fff'"
      :dotColorHover="'#fff'"
      :hoverSize="1.5"
    ></custom-cursor>
    <Lander />
  </div>
</template>

<script>
import Lander from "./components/Lander.vue";
import CustomCursor from "./components/CustomCursor.vue";

export default {
  name: "App",
  components: {
    Lander,
    CustomCursor
  }
};
</script>

<style>
html,
body {
  background-color: #0e0e0e;
}
* {
  cursor: none;
}
#app {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica,
    Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(253, 253, 249);
}
</style>
