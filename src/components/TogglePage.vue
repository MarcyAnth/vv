<template>
  <Opening :rainBool="toggleRainBool"/>
  <div :class="{ 'fade-out': toggleRainBool === null, 'fade-in': toggleRainBool === true, 'remove-comp': toggleRainBool === false }" v-if="toggleRainBool === true">
    <Rain />
  </div>
  <div :class="{ 'fade-out': toggleRainBool === null, 'remove-comp': toggleRainBool === true}" v-if="toggleRainBool === false">
    <Sun/>
  </div>
  <div>
    <button 
      @mouseover="setRain(false)"
      @mouseleave="resetRain"
      style="position:absolute; left: 40%; top: 50%; z-index: 100000"
      @click="itsAMatch"
    >Yes</button>
    <button 
      @mouseover="setRain(true)"
      @mouseleave="resetRain"
      @click="moveNoButton"
      :style="noButtonStyle"
      style="z-index: 1000000"
    >No</button>
  </div>
  <Match :slideIn="showMatchAnimation"/>
</template>

<script>
import Rain from './Rain.vue'
import Sun from './Sun.vue'
import Opening from './Opening.vue'
import Match from './Match.vue'

export default {
  name: 'TogglePage',
  components: {
    Rain, Sun, Opening, Match
  },
  data() {
    return {
      showMatchAnimation: false,
      toggleRainBool: null,
      noButtonStyle: {
        top: '50%',
        left: '60%',
        position: 'absolute'
      }
    };
  },
  methods: {
    setRain(value) {
      this.toggleRainBool = value;
    },
    itsAMatch() {
      this.showMatchAnimation = true;
      console.log('click',this.showMatchAnimation)
    },
    resetRain() {
      this.toggleRainBool = null;
    },
    moveNoButton() {
  const minX = 0;
  const maxX = window.innerWidth - 1000;
  const minY = 0;
  const maxY = window.innerHeight - 500;
  
  const newX = Math.floor(Math.random() * (maxX - minX)) + minX;
  const newY = Math.floor(Math.random() * (maxY - minY)) + minY;
  
  this.noButtonStyle = {
    top: `${newY}px`,
    left: `${newX}px`,
    position: 'absolute'
  };
}
  }
}
</script>

<style>

.button-container {
  position: absolute;
  top: 50%;
  left: 50%;
  z-index: 10000000;
  display: flex;
  gap: 10px;
  flex-direction: row-reverse;

}

.remove-comp {
  display: none;
}
</style>
