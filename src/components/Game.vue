<template>
  <div id="game" @click="generateObstacle()">
    <!-- <div class="play" @click="startGame()">Gioca!!</div> -->
    <div class="vhs-glitch"></div>
    <img
      src="../assets/img/car.gif"
      alt=""
      id="massaro"
      :style="massaroStyle"
      :class="{ idle: nowIdle }"
    />
    <div id="porcoddio" :style="obstacle"></div>
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
      faling: false,
      massaroStyle: {
        bottom: "30px",
      },
      //data per generateObstacle()
      obstacle: {
        position: "absolute",
        left: "",
        bottom: "0px",
        height: "200px",
        width: "200px",
        background: "orange",
      },
      obstaclePosition: 3000,
      obstacleMoving: null,
      ostacolo: document.getElementById("porcoddio"),
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
  computed: {
    randomTime() {
      return (
        Math.random() *
        3000(() => {
          return this.randomTime;
        })
      );
    },
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
      if (
        this.nowIdle == true &&
        this.nowJumping === false &&
        this.faling == false
      ) {
        this.nowJumping = true;
        this.nowIdle = false;
        console.log(this.nowIdle);
        this.jump = setInterval(() => {
          //cadi
          if (this.position === 300 || !this.nowJumping) {
            console.log("giu");
            clearInterval(this.jump);
            this.faling = true;
            this.fall = setInterval(() => {
              if (this.position === 30) {
                clearInterval(this.fall);
                this.faling = false;
                this.nowIdle = true;
              }
              this.position -= 10;
              this.massaroStyle.bottom = this.position + "px";
              this.nowJumping = false;
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
    generateObstacle() {
      const diocane = document.createElement("div");
      this.ostacolo.$appendChild(diocane);
      console.log(this.ostacolo);
      this.obstacle.left = this.obstaclePosition + "px";
      this.obstacleMoving = setInterval(() => {
        this.obstaclePosition -= 10;
        this.obstacle.left = this.obstaclePosition + "px";
      }, 20);
      // setTimeout(() => {
      //   document.createElement("div").classList.add("staticobs");
      // }, 20);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/game.scss";
.staticobs {
  z-index: 3;
  background-color: orange;
}
#porcoddio {
  z-index: 999;
  background-color: orange;
  div {
    background-color: wheat;
    height: 100px;
    width: 100px;
  }
}
</style>
