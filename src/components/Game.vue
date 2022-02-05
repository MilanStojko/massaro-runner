<template>
  <div id="game">
    <div class="play" @click="startGame()">Gioca!!</div>
    <img src="../assets/img/car.gif" alt="" id="massaro" />
    <div class="sky"></div>
    <div class="ground"></div>
  </div>
</template>

<script>
export default {
  name: "Game",
  data() {
    return {
      gameStart: false,
      gamePause: false,
      poits: 0,
      gameSpeed: 15,
    };
  },
  methods: {
    startGame() {
      if (!this.gameStart) {
        this.gameStart = true;
        console.log(this.gameStart);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/game.scss";
</style>
