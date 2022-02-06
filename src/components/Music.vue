<template>
  <div id="music">
    <audio controls autoplay loop>
      <source src="../assets/music/retro-music.mp3" type="audio/mpeg" />
      Il tuo browser non suppporta questo player musicale.
    </audio>
  </div>
</template>

<script>
export default {
  name: "Music",
};
</script>

<style lang="scss" scoped>
#music {
  z-index: 4;
  position: absolute;
  top: 20px;
  width: 200px;
  right: 20px;

  border-radius: 50px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  opacity: 0.1;
  transition: all 0.3s;

  &:hover {
    width: 20%;
    min-width: 250px;
    opacity: 1;
  }

  audio {
    width: 100%;
  }
}
</style>
