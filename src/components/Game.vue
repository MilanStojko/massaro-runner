<template>
  <div id="game">
    <!-- <div class="play" @click="startGame()">Gioca!!</div> -->
    <div class="vhs-glitch"></div>
    <img
      src="../assets/img/car.gif"
      alt=""
      id="massaro"
      :style="massaroStyle"
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
      nowJumping: false,
      position: 0,
      massaroStyle: {
        bottom: "0px",
      },
      wewe: null,
      jammja: null,
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
    commandJump(e) {
      if (e.code === "Space") {
        console.log("Spacebar premuta");
        e.preventDefault();
        if (this.nowIdle == true && this.nowJumping === false) {
          this.nowJumping = true;
          this.massaroJump();
        }
      }
    },
    massaroJump() {
      this.wewe = setInterval(() => {
        //cadi
        if (this.position === 300) {
          console.log("giu");
          clearInterval(this.wewe);
          this.jammja = setInterval(() => {
            if (this.position === 0) {
              clearInterval(this.jammja);
            }
            this.position -= 30;
            this.massaroStyle.bottom = this.position + "px";
          }, 20);
        }
        //salta
        this.position += 30;
        this.massaroStyle.bottom = this.position + "px";
      }, 20);
    },
    massaroLanding(e) {
      if (e.code === "Space") {
        console.log("Spacebar rilasciata");

        if (this.nowJump == true) {
          this.nowJump = false;
          this.nowFall = true;

          setTimeout(() => {
            this.nowFall = false;
            this.nowIdle = true;
          }, 500);
        }
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/game.scss";
</style>
