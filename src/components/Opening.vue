<template>
    <div  v-if="rainBool === null" style="display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;">
        <h1>Hello Vicky,
            will you be my valentines?
        </h1>
        <img class="beating" src="../assets/pngegg.png" alt="">
    </div>
  </template>

<script>
export default {
  name: 'Opening',
  props: {
    rainBool: null
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

.beating {
      animation: beatingHeart 2s infinite alternate;
    }

    @keyframes beatingHeart {
      0% {
        transform: scale(1);
      }
      100% {
        transform: scale(1.2);
      }
  }
</style>