<template>
  <div id="game">
    <!-- <div class="play" @click="startGame()">Gioca!!</div> -->
    <div class="vhs-glitch"></div>
    <img
      src="../assets/img/car.gif"
      alt=""
      id="massaro"
      :class="{ idle: nowIdle, jump: nowJump, fall: nowFall }"
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
      points: 0,
      gameSpeed: 1,
      nowIdle: true,
      nowJump: false,
      nowFall: false,
      nowFloating: false,
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

        this.nowIdle = false;
        this.nowJump = true;
      }
    },
    massaroLanding(e) {
      if (e.code === "Space") {
        console.log("Spacebar rilasciata");

        setTimeout(() => {
          this.nowJump = false;
          this.nowFall = true;
        }, 500);
        setTimeout(() => {
          this.nowFall = false;
          this.nowIdle = true;
        }, 1000);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/game.scss";
</style>
