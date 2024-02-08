<template>
  <div>
    <video
        id="my-video"
        class="video-js"
        controls
        ref="video"
        preload="auto"
        width="640"
        height="264"
        data-setup="{}"
    >
      <source src="https://rcemmsqtyk.a.trbcdn.net/cdn/nayozona32/file_example_mp4_1280_10mg.mp4" />
      <p class="vjs-no-js">
        To view this video please enable JavaScript, and consider upgrading to a
        web browser that
        <a href="https://videojs.com/html5-video-support/" target="_blank">supports HTML5 video</a>
      </p>
    </video>
  </div>
</template>

<script>
import videojs from 'video.js'
import 'video.js/dist/video-js.css'

export default {
  name: 'VideoJsComponent',
  mounted() {
    this.player = videojs(this.$refs.video)
  },
  beforeDestroy() {
    if (this.player) {
      this.player.dispose()
    }
  }
}
</script>
