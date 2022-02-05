<template>
  <div id="game">
    <!-- <div class="play" @click="startGame()">Gioca!!</div> -->
    <img
      src="../assets/img/car.gif"
      alt=""
      id="massaro"
      :class="{ jump: jump, fall: fall }"
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
      if (!this.jump) {
        setTimeout(() => {
          this.jump = true;
          if (this.jump == true) {
            setTimeout(() => {
              this.fall = true;
            }, 500);
          }
        }, 0);
        this.jump = false;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/game.scss";
</style>
