<template>
  <div id="app">
    <img src="./assets/img/Ribbon Alpha.png" alt="" id="ribbon" />
    <img
      src="./assets/img/Massaro-Runner-logo-nolights.png"
      alt="Massaro Runner"
      id="logo"
    />
    <Game />

    <Info />
    <div class="background"></div>
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
