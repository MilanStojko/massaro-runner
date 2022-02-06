<template>
  <div id="app">
    <div id="logo">Massaro Runner 🏃</div>
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
