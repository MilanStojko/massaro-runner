<template>
  <div id="game">
    <!-- <div class="play" @click="startGame()">Gioca!!</div> -->
    <div class="vhs-glitch"></div>
    <img
      src="../assets/img/car.gif"
      alt=""
      id="massaro"
      :style="massaroStyle"
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
      nowJumping: false,
      position: 30,
      massaroStyle: {
        bottom: "30px",
      },
      jump: null,
      fall: null,
    };
  },
  created() {
    document.addEventListener("keydown", (e) => {
      this.commandJump(e);
    });
    document.addEventListener("keyup", (e) => {
      this.stopJump(e);
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
        this.massaroJump();
      }
    },
    massaroJump() {
      if (this.nowIdle == true && this.nowJumping === false) {
        this.nowJumping = true;
        this.jump = setInterval(() => {
          //cadi
          if (this.position === 300 || !this.nowJumping) {
            console.log("giu");
            clearInterval(this.jump);
            this.fall = setInterval(() => {
              if (this.position === 30) {
                clearInterval(this.fall);
                this.nowJumping = false;
              }
              this.position -= 10;
              this.massaroStyle.bottom = this.position + "px";
            }, 20);
          }
          //salta
          this.position += 10;
          this.massaroStyle.bottom = this.position + "px";
        }, 20);
      }
    },
    stopJump() {
      this.nowJumping = false;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/game.scss";
</style>
