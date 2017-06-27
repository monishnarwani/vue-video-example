<template>
  <div>
    <div data-vimeo-id="19231868" data-vimeo-width="640" id="handstick"></div>
    <div data-vimeo-url="https://vimeo.com/76979871" id="playertwo"></div>
  </div>
</template>

<script>
import Player from '@vimeo/player'

export default {
  mounted() {
    var handstickPlayer = new Player('handstick');
       handstickPlayer.on('play', function() {
           console.log('played the handstick video!');
       });

       var playerTwoPlayer = new Player('playertwo');
       playerTwoPlayer.on('play', function() {
           console.log('played the player 2.0 video!');
       });
  }
}

</script>
