<template>
  <div class="plyr__video-embed" id="plyr-video">
    <iframe
        class="video-foreground"
        src="https://player.vimeo.com/video/226053498?loop=false&amp;byline=false&amp;portrait=false&amp;title=false&amp;speed=true&amp;transparent=0&amp;controls=0&amp;gesture=media"
        allowfullscreen
        allowtransparency
        allow="autoplay"
    ></iframe>
  </div>
</template>

<script>
import Plyr from 'plyr'
import 'plyr/dist/plyr.css'

export default {
  name: 'PlyrComponent',
  mounted() {

    const controls = ['play-large', 'play', 'progress', 'current-time', 'mute', 'volume', 'pip', 'airplay', 'fullscreen']

    const video = document.getElementById('plyr-video')
    this.player = new Plyr(video, {controls})
  },
  beforeDestroy() {
    this.player.destroy()
  }
}
</script>


<!--//.video-background {-->
<!--//  background: #000;-->
<!--//  position: fixed;-->
<!--//  top: 0;-->
<!--//  right: 0;-->
<!--//  bottom: 0;-->
<!--//  left: 0;-->
<!--//  z-index: -99;-->
<!--//}-->
<!--//.video-foreground,-->
<!--//.video-background iframe {-->
<!--//  position: absolute;-->
<!--//  top: 0;-->
<!--//  left: 0;-->
<!--//  width: 100%;-->
<!--//  height: 100%;-->
<!--//}-->

<!--//@media (min-aspect-ratio: 16/9) {-->
<!--//  .video-foreground {-->
<!--//    height: 300%;-->
<!--//    top: -100%;-->
<!--//  }-->
<!--//}-->
<!--//@media (max-aspect-ratio: 16/9) {-->
<!--//  .video-foreground {-->
<!--//    width: 300%;-->
<!--//    left: -100%;-->
<!--//  }-->
<!--//}-->

<!--@media all and (max-width: 600px) {-->
<!--.vid-info {-->
<!--width: 50%;-->
<!--padding: 0.5rem;-->
<!--}-->
<!--.vid-info h1 {-->
<!--margin-bottom: 0.2rem;-->
<!--}-->
<!--}-->
<!--@media all and (max-width: 500px) {-->
<!--.vid-info .acronym {-->
<!--display: none;-->
<!--}-->
<!--}-->
<style>
.plyr__video-embed {
  width: 500px;
}
</style>