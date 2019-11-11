<template>
  <div>
    <div class="grid-container">
      <div class="grid-x grid-padding-x">
        <div class="large-12 cell">
          <video ref="videoPlayer" class="video-js"></video>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import videojs from 'video.js'
import 'video.js/dist/video-js.css'
export default {
  name: 'VideoPlayer',
  props: {
    options: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  data() {
    return {
      player: null
    }
  },
  mounted() {
    this.player = videojs(
      this.$refs.videoPlayer,
      this.options,
      function onPlayerReady() {}
    )
  }
}
</script>
<style scoped>
p {
  font-size: 1.2em;
}

.grid-padding-x > .cell {
  padding-bottom: 0.9375rem;
  padding-top: 0.9375rem;
}
.video-js {
  width: auto;
}
</style>
