<template>
<div class="test" style="z-index: 999">
  <div style="position: absolute; left: 35%; top:5%">
  <h1>I hope you never hover over this...</h1>
  <h1>Press the button, see what happens :D</h1>
</div>
    <Totoro/>
</div>

</template>
 
<script>

import Totoro from './Totoro.vue'
export default {
  name: 'Rain',
  components: {
    Totoro
  },
  props: {
    backgroundColor: ''
  },
  data() {
    return {
    };
  },
  methods: {
    toggleRain() {      
      let hrElement;
      let counter = 100;
      let checking = document.querySelector('.test')
      for (let i = 0; i < counter; i++) {
        hrElement = document.createElement("HR");
        if (i == counter - 1) {
          hrElement.className = "thunder";
        } else {
          hrElement.style.left = Math.floor(Math.random() * window.innerWidth) + "px";
          hrElement.style.animationDuration = 0.2 + Math.random() * 0.3 + "s";
          hrElement.style.animationDelay = Math.random() * 5 + "s";
        }
       checking.appendChild(hrElement);
      }


      console.log(
        "There are " +
        document.querySelectorAll("hr").length +
        " <hr> tags in this project :)"
      );
    }
  },
  mounted() {
    this.toggleRain();
  }
}
       
</script>


<style>
  * {
    margin: 0;
    padding: 0;
  }
 
  :root {
    --thunder-duration: 5s;
    --thunder-delay: 10s;
  }
 
  .test {
    background-image: linear-gradient(to bottom, #030420, #000000 70%);
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100vw;
    height: 100vh;
    overflow: none;
  }
 
  hr.thunder {
    border: unset;
    position: absolute;
    width: 100vw;
    height: 100vh;
    animation-name: thunder;
    animation-duration: var(--thunder-duration);
    animation-timing-function: linear;
    animation-delay: var(--thunder-delay);
    animation-iteration-count: infinite;
    z-index: -100;
  }
 
  hr:not(.thunder) {
    width: 50px;
    border-color: transparent;
    border-right-color: rgba(255, 255, 255, 0.7);
    border-right-width: 50px;
    position: absolute;
    bottom: 100%;
    transform-origin: 100% 50%;
    animation-name: rain;
    animation-duration: 1s;
    animation-timing-function: linear;
    animation-iteration-count: infinite;
  }
 
  @keyframes rain {
    from {
      transform: rotate(105deg) translateX(0);
    }
    to {
      transform: rotate(105deg) translateX(calc(100vh + 20px));
    }
  }
 
  @keyframes thunder {
    0% {
      background-color: transparent;
    }
    1% {
      background-color: white;
    }
    2% {
      background-color: rgba(255, 255, 255, 0.8);
    }
    8% {
      background-color: transparent;
    }
  }
</style>