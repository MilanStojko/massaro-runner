<template>
  <div id="game">
    <!-- <div class="play" @click="startGame()">Gioca!!</div> -->
    <div class="vhs-glitch"></div>
    <img
      src="../assets/img/car.gif"
      alt=""
      id="massaro"
      :class="{ jump: jump, fall: fall, floating: floating }"
    />
    <div class="ground">
      <div class="flow"></div>
    </div>
    <div class="sky"></div>
    <div class="animated-bg">
      <video autoplay muted loop>
        <source src="../assets/video/background.mp4" type="video/mp4" />
      </video>
    </div>
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
  created() {
    document.addEventListener("keydown", (e) => {
      this.massaroJump(e);
    });
    document.addEventListener("keyup", (e) => {
      this.massaroLanding(e);
    });
  },
  methods: {
    // startGame() {
    //   if (!this.gameStart) {
    //     this.gameStart = true;
    //     console.log(this.gameStart);
    //   }
    // },
    massaroJump(e) {
      if (e.code === "Space") {
        console.log("Spacebar premuta");

        e.preventDefault();
        this.jump = true;
        setTimeout(() => {
          this.jump = false;
          this.floating = true;
        }, 500);
      }
    },
    massaroLanding(e) {
      if (e.code === "Space") {
        console.log("Spacebar rilasciata");
        setTimeout(() => {
          this.floating = false;
          this.fall = true;
        }, 1500);
        setTimeout(() => {
          this.fall = false;
        }, 2000);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/game.scss";
</style>
