<template>
  <div id="game">
    <img src="../assets/img/car.gif" alt="" id="massaro" />
    <div class="sky"></div>
    <div class="ground"></div>
  </div>
</template>

<script>
export default {
  name: "Game",
  data(){
    return{
      gameStart : false,
      

    }
  }
};
</script>

<style lang="scss" scoped>
#game {
  position: relative;
  // margin: 50px 0 0 0;
  height: 480px;
  width: 100%;
  // border: 1px solid red;
}

#massaro {
  z-index: 3;
  position: absolute;
  bottom: 120px;
  left: 100px;
  transform: scale(2);
}

.sky {
  z-index: 1;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: #000;
  background: linear-gradient(
    0deg,
    rgba(71, 9, 122, 1) 0%,
    rgba(0, 0, 0, 1) 85%,
    rgba(0, 0, 0, 1) 100%
  );
}

.ground {
  z-index: 2;
  position: absolute;
  bottom: 0;
  height: 130px;
  width: 100%;
  background: rgb(31, 12, 82);
  background: linear-gradient(
    0deg,
    rgba(0, 0, 0, 1) 0%,
    rgba(33, 14, 61, 1) 65%,
    rgba(61, 26, 113, 1) 100%
  );

  box-shadow: 0 -10px 30px rgba(0, 0, 0, 0.4);
}
</style>
