<template>
<div  @mouseover="showMatch" class="container">
  <h1 style="position: absolute; top: 30%; left: 45%">Love is in the air</h1>
<div class="sun">
  <div class="circle"></div>
  <div class="eyes">
    <span class="left"></span>
    <span class="right"></span>
  </div>
  <div class="sunrays">
    <span />
    <span />
    <span />
  </div>
</div>
</div>
</template>
 
<script>



export default {
  name: 'Sun',
  components: {

  },
  props: {
  },
  data() {
    return {
    };
  },
 
}
       
</script>


<style scoped lang="scss">
$size: 130px;
$yellow: #FFDD4A;
$blue: #85C7F2;


//mixins
@mixin rotate($deg){
  -ms-transform: rotate($deg);
  -webkit-transform: rotate($deg);
  transform: rotate($deg);
}
@mixin animate($name, $seconds, $direction, $length){
  -webkit-animation:$name $seconds $direction $length;
  -moz-animation:$name $seconds $direction $length;
  animation:$name $seconds $direction $length;
}
@mixin eye-shape($height, $width, $radius){
    height: $height;
    width: $width;
    border-radius: $radius;
}


.container{
  height: 100vh;
  width: 100vw;
  background: $blue;
  margin: 0;
  z-index: 1000;
  position: relative;
  overflow:hidden;
}


.sun{
  height: $size;
  width: $size;
  position: relative;
  margin: 0 auto;
  top: calc(50% - 65px);
  .sunrays{
    @include animate(spin, 15s, linear, infinite);
    box-shadow: 0px 0px 100px lighten($yellow, 10%);
    height: $size;
    width: $size;
  }
}


.circle{
  height: $size;
  width: $size;
  z-index: 1;
  background: lighten($yellow, 10%);
  position: absolute;
  border-radius: 50%;
}


.sunrays span{
  background: $yellow;
  width:$size;
  height:$size;
  position: absolute;
  &:first-child{@include rotate(30deg);}
  &:nth-child(2){@include rotate(60deg);}
}


.eyes{
  position: relative;
  top: 50px;
  z-index: 2;
  .left, .right{
    background: black;
    position: absolute;
    @include eye-shape(8px, 8px, 50%);
    @include animate(blink, 2.5s, linear, infinite);
  }
  .left{left: 47%;}
  .right{left: 15%;}
}


//animations
@keyframes spin {
  0% {-webkit-transform: rotate(0deg); }
  100% { -webkit-transform: rotate(360deg); }
}
@-moz-keyframes spin {
  0% {-moz-transform: rotate(0deg); }
  100% { -moz-transform: rotate(360deg); }
}
@keyframes blink {
  0% { @include eye-shape(8px, 8px, 50%); }
  5% { @include eye-shape(1px, 8px, 0); }
  10% { @include eye-shape(8px, 8px, 50%); }
}
</style>