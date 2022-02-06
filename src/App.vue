<template>
  <div id="app">
    <img src="./assets/img/Ribbon-Alpha.png" alt="" id="ribbon" />
    <img
      src="./assets/img/Massaro-Runner-logo-nolights.png"
      alt="Massaro Runner"
      id="logo"
    />
    <div class="small-screen">
      Mi dispiace il tuo schermo è troppo piccolo per poter giocare!
    </div>
    <Game />
    <Music />
    <Info />
    <!-- <div class="neonbar"></div> -->
    <div class="background"></div>
  </div>
</template>

<script>
import Game from "./components/Game.vue";
import Info from "./components/Info.vue";
import Music from "./components/Music.vue";

export default {
  name: "App",
  components: {
    Game,
    Info,
    Music,
  },
};
</script>

<style lang="scss">
@import "./assets/style/global.scss";
</style>
