<script lang="ts">
import Player from '@vimeo/player';
import {ref, onMounted} from 'vue'

export default {
  setup() {
    const vi = ref(null)
    onMounted(() => {
      // элемент DOM будет определён в ref после первоначальной отрисовки
      console.log(vi.value) // <div>Это корневой элемент</div>


      const options = {
        url: "https://player.vimeo.com/video/226053498?h=a1599a8ee9",
        width: 640,
        controls: false,
        byline: false,
        fullscreen: true,
        vimeo_logo: false,
        portrait: false,
        interactive_markers: false,
        chromecast: false,
        title: false,
        playsinline: true,
        loop: true
      };

      const player = new Player("made-in-ny", options);

      player.setVolume(0);

      player.on('play', function () {
        console.log('played the video!');
      });

      // setTimeout(() => {
      //   console.log("start play")
      //   player.play()
      //   console.log("end play")
      // }, 1500)
      // setTimeout(() => {
      //   console.log("start play")
      //   player.pause()
      //   console.log("end play")
      // }, 3500)
      // setTimeout(() => {
      //   console.log("start play")
      //   player.requestFullscreen()
      //   console.log("end play")
      // }, 500)
      // setTimeout(() => {
      //   console.log("start play")
      //   player.exitFullscreen()
      //   console.log("end play")
      // }, 4500)
      // console.log(player)
      // window.player = player;
    })

    return {
      vi
    }
  }
}
</script>

<template>
  <div ref="vi" id="made-in-ny"></div>
</template>

<style scoped>

</style>