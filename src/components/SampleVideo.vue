<template>
  <div>
    <d-player :video="video" lang="en" @play="videoPlayed(event)" @ended="videoEnded(event)"></d-player>
    <!-- <d-player  :video="video"  ref="videoPlayer"
                             :options="playerOptions"
                             @play="onPlayerPlay($event)"
                             @pause="onPlayerPause($event)"
                             @ended="onPlayerEnded($event)"
                             @loadeddata="onPlayerLoadeddata($event)"
                             @waiting="onPlayerWaiting($event)"
                             @playing="onPlayerPlaying($event)"
                             @timeupdate="onPlayerTimeupdate($event)"
                             @canplay="onPlayerCanplay($event)"
                             @canplaythrough="onPlayerCanplaythrough($event)"
                             @ready="playerReadied"
                             @statechanged="playerStateChanged($event)">
              </d-player> -->
  </div>
</template>
<script>
  import VueDPlayer from 'vue-dplayer'
  export default {
    components: {
      'd-player': VueDPlayer
    },
    data() {
      return {
        video: {
          url: 'https://player.vimeo.com/external/222785177.hd.mp4?s=212f00f9e448dca2f62be6b74834feef959b68d4&profile_id=119',
          pic: 'https://www.planwallpaper.com/static/images/Light-Wood-Background-Wallpaper.jpg'
        },
        playerOptions: {
                  // component options
                  start: 0,
                  playsinline: false,
                  // videojs options
                  muted: true,
                  language: 'en',
                  playbackRates: [0.7, 1.0, 1.5, 2.0],
                  sources: [{
                    type: "video/mp4",
                    src: "https://player.vimeo.com/external/222785177.hd.mp4?s=212f00f9e448dca2f62be6b74834feef959b68d4&profile_id=119"
                  }]
                }
      }
    },
    methods: {
      videoPlayed(player) {
        console.log('video played', player)
      },
      videoEnded(player) {
        console.log('video Ended', player)
      },
      onPlayerPlay(player) {
             console.log('player play!', player)
           },
           onPlayerPause(player) {
             console.log('player pause!', player)
           },
           onPlayerEnded(player) {
             console.log('player ended!', player)
           },
           onPlayerLoadeddata(player) {
             console.log('player Loadeddata!', player)
           },
           onPlayerWaiting(player) {
             console.log('player Waiting!', player)
           },
           onPlayerPlaying(player) {
             console.log('player Playing!', player)
           },
           onPlayerTimeupdate(player) {
             console.log('player Timeupdate!', player.currentTime())
           },
           onPlayerCanplay(player) {
             console.log('player Canplay!', player)
           },
           onPlayerCanplaythrough(player) {
             console.log('player Canplaythrough!', player)
           },
           // or listen state event
           playerStateChanged(playerCurrentState) {
             console.log('player current update state', playerCurrentState)
           },
           // player is ready
           playerReadied(player) {
             console.log('example 01: the player is readied', player)
           }
    }
  }
</script>
