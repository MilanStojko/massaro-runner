<template>
  <div id="app">
    <div id="logo">Massaro Runner 🏃</div>
    <Game />
    <Info />
    <div class="animated-bg">
      <video autoplay muted loop>
        <source src="./assets/video/background.mp4" type="video/mp4" />
      </video>
    </div>
  </div>
</template>

<script>
import Game from "./components/Game.vue";
import Info from "./components/Info.vue";

export default {
  name: "App",
  components: {
    Game,
    Info,
  },
};
</script>

<style lang="scss">
@import "./assets/style/global.scss";
</style>
