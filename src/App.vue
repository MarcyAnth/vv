<template>
  
<TogglePage/>
</template>


<script>
import TogglePage from './components/TogglePage.vue'

export default {
  name: 'App',
  components: {
    TogglePage
  },
  data() {
    return {

    };
  },
  methods: {
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Honk&display=swap');



body {
  overflow: hidden;
  font-family: "Honk", system-ui;
}

button {
  min-width: 50px;
  aspect-ratio: 1/1;
  border: 1px solid white;
  border-radius: 5px;
  cursor: pointer;
  background-color: #F8C8DC;
}

.fade-in {
  animation: fadeIn 0.5s;
}

.fade-out {
  animation: fadeIn 0.5s;
  animation-direction: reverse;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  } 
  100% {
    opacity: 1;
  }
}

@keyframes slideInLeft {
    0% {
    left: -50%;
    z-index: 10000000;
    }
    100% {
      left: 10%;
      z-index: 10000000;
      bottom: 60%;
    }
}

@keyframes slideInRight {
    0% {
    right: -50%;
    z-index: 10000000;
    }
    100% {
      right: 10%;
      z-index: 10000000;
      bottom: 60%;
    }
}


</style>
