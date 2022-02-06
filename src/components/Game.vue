<template>
  <div id="game">
    <!-- <div class="play" @click="startGame()">Gioca!!</div> -->
    <img
      src="../assets/img/car.gif"
      alt=""
      id="massaro"
      :class="{ jump: jump, fall: fall, floating: floating }"
      @click="massaroJump()"
    />
    <div class="sky"></div>
    <div class="ground"></div>
  </div>
</template>

<script>
export default {
  name: "Game",
  data() {
    return {
      gameStart: true,
      gamePause: false,
      poits: 0,
      gameSpeed: 15,
      jump: false,
      fall: false,
      floating: false,
    };
  },
  methods: {
    // startGame() {
    //   if (!this.gameStart) {
    //     this.gameStart = true;
    //     console.log(this.gameStart);
    //   }
    // },
    massaroJump() {
      this.jump = true;
      setTimeout(() => {
        this.jump = false;
        this.floating = true;
      }, 500);
      setTimeout(() => {
        this.floating = false;
        this.fall = true;
      }, 1500);
      setTimeout(() => {
        this.fall = false;
      }, 2000);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/game.scss";
</style>
