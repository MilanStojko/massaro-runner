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
  components: { Game },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;

  // Da decommentare a fine lavoro
  // -webkit-user-select: none;
  // -ms-user-select: none;
  // user-select: none;

  // Da decommentare in mental breakdown
  // border: 2px solid red;
}

body {
  border-top: 15px solid rgb(125, 0, 228);
  background: #000;
  font-family: Arial, Helvetica, sans-serif;
  color: #fff;
}

#logo {
  margin: 50px auto 50px auto;
  padding: 0 20px;
  width: fit-content;
  font-size: 3rem;
  letter-spacing: 5px;
  // border-bottom: 3px solid #fff;
}
</style>
