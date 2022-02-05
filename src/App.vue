<template>
  <div id="app">
    <div id="logo">Massaro Runner 🏃</div>
    <Game />
  </div>
</template>

<script>
import Game from "./components/Game.vue";
export default {
  name: "App",
  components: { 
    Game 
    },
};
</script>

<style lang="scss">
@import "./assets/style/global.scss";
</style>
