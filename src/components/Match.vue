<template>
    <div>
        <img :class="{ 'slide-in-left': slideIn, 'left-off-screen' :!slideIn}" src="../assets/vicky.jpg" alt="vicky">
        <img :class="{ 'slide-in-right': slideIn, 'left-off-screen' :!slideIn}" class="right-off-screen" src="../assets/marc.jpg" alt="marc">
    </div>
  </template>

<script>
export default {
  name: 'Match',
  props: {
    slideIn: false
  },
  data() {
    return {

    };
  },
  methods: {
        
    },
  }
</script>

<style>
img {
    height: 300px;
    aspect-ratio: 1/1;
}

.left-off-screen {
    left: -50%;
    position: absolute;
}

.right-off-screen {
    right: -50%;
    position: absolute;
} 

.slide-in-left {
    animation: slideInLeft 1s;
    position: absolute;
    left: 10%;
    bottom: 60%;
    z-index: 100000;
}


.slide-in-right {
    animation: slideInRight 1s;
    position: absolute;
    right: 10%;
    bottom: 60%;
    z-index: 100000;
}
</style>