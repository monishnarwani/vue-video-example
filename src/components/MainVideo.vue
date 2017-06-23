<template>
  <div>
    <video :id="identifier" :src="source" controls></video>
  </div>
</template>
<script>

  export default {
    props: ['source','identifier'],
    created() {
      window.eventBus.$on('video-Played-' + this.identifier, () => {
        console.log('video-Played' + this.identifier)
      })
      window.eventBus.$on('video-ended-' + this.identifier, () => {
        console.log('video-ended' + this.identifier)
      })
    },
    mounted() {
      this.videoEl = document.getElementById(this.identifier)
      this.videoEl.onplay =  () => {
        console.log(this.identifier)
        window.eventBus.$emit('video-Played-' + this.identifier)
      }
      this.videoEl.onended = () => {
        window.eventBus.$emit('video-ended-' + this.identifier)
      }
    },
    data() {
      return {
        videoEl: null
      }
    }
  }
</script>
<style>
  video::-internal-media-controls-download-button {
      display:none;
  }

  video::-webkit-media-controls-enclosure {
      overflow:hidden;
  }

  video::-webkit-media-controls-panel {
      width: calc(100% + 30px); /* Adjust as needed */
  }
</style>
