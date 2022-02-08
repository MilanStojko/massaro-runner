<template>
  <div id="game">
    <div class="vhs-glitch"></div>
    <img
      src="../assets/img/car.gif"
      alt=""
      id="massaro"
      :style="massaroStyle"
      :class="{ idle: nowIdle }"
    />
    <div class="obstacle"></div>
    <div class="ground">
      <div class="flow"></div>
    </div>
    <div class="palm2"></div>
    <div class="palm1"></div>
    <div class="city2"></div>
    <div class="city1"></div>
    <div class="sky"></div>
  </div>
</template>

<script>
export default {
  name: "Game",
  data() {
    return {
      //data per game enviorment
      gameStart: true,
      gamePause: false,
      points: 0,
      gameSpeed: 1,
      //data per massaroJump()
      nowIdle: true,
      nowJumping: false,
      position: 30,
      jump: null,
      fall: null,
      falling: false,
      massaroStyle: {
        bottom: "30px",
      },
      //data per generateObstacle()
      // obstacle: {
      //   position: "absolute",
      //   left: "",
      //   bottom: "0px",
      //   height: "200px",
      //   width: "200px",
      //   background: "orange",
      // },
      // obstaclePosition: 3000,
      // obstacleMoving: null,
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
  mounted() {
    this.generateObstacle();
  },
  // computed: {
  //   randomTime() {
  //     return (
  //       Math.random() *
  //       3000(() => {
  //         return this.randomTime;
  //       })
  //     );
  //   },
  // },
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
      if (
        this.nowIdle == true &&
        this.nowJumping === false &&
        this.falling == false
      ) {
        this.nowJumping = true;
        this.nowIdle = false;
        console.log(this.nowIdle);
        this.jump = setInterval(() => {
          //cadi
          if (this.position === 300 || !this.nowJumping) {
            console.log("giu");
            clearInterval(this.jump);
            this.falling = true;
            this.fall = setInterval(() => {
              if (this.position === 30) {
                clearInterval(this.fall);
                this.falling = false;
                this.nowIdle = true;
              }
              this.position -= 10;
              this.massaroStyle.bottom = this.position + "px";
              this.nowJumping = false;
            }, 10);
          }
          //salta
          this.position += 10;
          this.massaroStyle.bottom = this.position + "px";
        }, 10);
      }
    },
    stopJump() {
      this.nowJumping = false;
    },
    generateObstacle() {
      const obstacle = document.createElement("div");
      obstacle.classList.add("obstacle");
      document.getElementById("game").appendChild(obstacle);
      console.log(obstacle);
      // obstacle.left = this.obstaclePosition + "px";
      // this.obstacleMoving = setInterval(() => {
      //   this.obstaclePosition -= 10;
      //   this.obstacle.left = this.obstaclePosition + "px";
      // }, 15);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/game.scss";
.obstacle {
  z-index: 10;
  position: absolute;
  bottom: 0;
  right: 0;
  background-color: orange;
  height: 200px;
  width: 200px;
}
</style>
