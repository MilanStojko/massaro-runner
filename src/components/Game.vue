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
      if (!this.jump) {
        this.jump = true;
        if (this.jump == true) {
          this.floating = true;
          setTimeout(() => {
            this.fall = true;
            this.floating = false;
          }, 300);
          this.fall = true;
          this.floating = false;
          console.log(this.jump);
          console.log(this.fall);
          console.log(this.floating);
        }
      }
      setTimeout(() => {
        this.fall = false;
        this.jump = false;
        console.log(this.jump);
        console.log(this.fall);
        console.log(this.floating);
      }, 300);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/game.scss";
</style>
