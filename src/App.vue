<template>
  <div id="app">
    <!-- <main-video :identifier="identifier1" :source="source" @onplay="videoPlayed" @onended="videoEnded" @error="errorOccured" :poster="imgsrc"></main-video> -->
  <!--   <i :class="{'fa fa-circle-o-notch fa-spin' : loading}" style="font-size:48px;"></i>
    <main-video :identifier="identifier2" :source="source" @onplay="videoPlayed" @onended="videoEnded" @error="errorOccured" :poster="imgsrc" @waiting="loading = true" @playing="loading = false" @canplay="loading = false" @seeked="loading = true"></main-video> -->
  <vimeo-player></vimeo-player>

  </div>
</template>

<script>
import MainVideo from './components/MainVideo'
import VimeoPlayer from './components/VimeoPlayer'
export default {
  name: 'app',
  components: {
    VimeoPlayer
  },
  data() {
    return {
      source: 'https://player.vimeo.com/external/223273160.sd.mp4?s=b3881800205e0fff9fb18b95c4d1e16fb1bd56a4&profile_id=164',
      imgsrc: 'https://upload.wikimedia.org/wikipedia/commons/3/30/Googlelogo.png',
      identifier1: 'video1',
      identifier2: 'video2',
      loading: true
    }
  },
  methods: {
    videoPlayed(event) {
      console.log('played', event.srcElement.id)
    },
    videoEnded(event) {
      console.log('ended', event.srcElement.id)
    },
    errorOccured(event) {
      console.log('error occured')
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
