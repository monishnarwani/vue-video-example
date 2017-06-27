<template>
  <div>
    <video :id="identifier" :src="source" :poster="poster" controls preload="auto"></video>
  </div>
</template>

<script>
export default {
  props: ['source','identifier', 'poster'],
  created() {
    console.log(this.poster)
  },
  mounted() {
    this.videoEl = document.getElementById(this.identifier)
    // this.videoEl.currentTime = 30
    // this.videoEl.playbackRate += 1
    this.videoEl.onplay =  (event) => {
      this.$emit('onplay', event)
    }
    this.videoEl.onended = (event) => {
      this.$emit('onended', event)
    }
    this.videoEl.onerror = (event) => {
      this.$emit('error', event)
    }
    this.videoEl.onwaiting = (event) => {
      console.log('waiting')
      this.$emit('waiting')
    }
    this.videoEl.onprogress = (event) => {
      console.log('progress')
      this.$emit('progress', event)
    }
    this.videoEl.onplaying = (event) => {
      console.log('playing')
      this.$emit('playing')
    }
    this.videoEl.oncanplay = (event) => {
      console.log('canplay')
      this.$emit('canplay')
    }
    this.videoEl.onseeked = (event) => {
      console.log('seeked')
      this.$emit('seeked')
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
