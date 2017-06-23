<template>
  <div>
    <video @onplay="play()" id="myvid" class="vid" src="https://player.vimeo.com/external/222785177.hd.mp4?s=212f00f9e448dca2f62be6b74834feef959b68d4&profile_id=119" controls></video>
  </div>
</template>
<script>
  export default {
    methods: {
      play() {
        console.log('play')
      },
      stop() {
        console.log('stop')
      }
    }
  }
</script>

<style>
  .vid {
    width: 500px;
    height: 500px;
    margin: 100px;
    padding: 50px;
  }
</style>
