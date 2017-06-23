<template>
  <div id="app">
    <!-- <sample-video></sample-video> -->
    <!-- <my-video></my-video> -->
    <main-video :identifier="identifier1" :source="source"></main-video>
    <main-video :identifier="identifier2" :source="source"></main-video>
  </div>
</template>

<script>
// import SampleVideo from './components/SampleVideo'
// import MyVideo from './components/MyVideo'
import MainVideo from './components/MainVideo'
export default {
  name: 'app',
  components: {
    // SampleVideo,
    // MyVideo,
    MainVideo
  },
  data() {
    return {
      source: 'https://player.vimeo.com/external/222785177.hd.mp4?s=212f00f9e448dca2f62be6b74834feef959b68d4&profile_id=119',
      identifier1: 'video1',
      identifier2: 'video2'
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
