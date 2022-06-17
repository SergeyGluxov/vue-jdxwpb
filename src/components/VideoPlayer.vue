<script>
import fluidPlayer from 'fluid-player';
export default {
  data() {
    return {
      player: null,
    };
  },
  mounted() {
    this.player = fluidPlayer(this.$refs.myVideoPlayer);
  },
  destroyed() {
    if (!this.player) {
      return;
    }

    this.player.destroy();
  },
};
</script>

<template>
  <div class="fluid-component">
    <video ref="myVideoPlayer">
      <source
        src="https://cdn.fluidplayer.com/videos/valerian-1080p.mkv"
        data-fluid-hd
        title="1080p"
        type="video/mp4"
      />
    </video>
  </div>
</template>

<style scoped>
@import '~fluid-player/src/css/fluidplayer.css';

div.fluid-component,
div.fluid-component > video {
  width: 100%;
  height: 100%;
}
</style>
