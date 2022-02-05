<template>
  <div id="game">
    <img src="../assets/img/car.gif" alt="" id="massaro" />
    <div class="sky"></div>
    <div class="ground"></div>
  </div>
</template>

<script>
export default {
  name: "Game",
  data(){
    return{
      gameStart : false,
      

    }
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/style/game.scss";
</style>
