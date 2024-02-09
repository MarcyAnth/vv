<template>
<div id="wrapper">
  <div id="totoro">
    <div id="totoro_top"></div>
    <div id="totoro_face">
      <div class="ear left"></div>
      <div class="ear right"></div>
      <div class="eye left_eye"></div>
      <div class="eye right_eye"></div>
      <div class="nose"></div>
      <div class="mouth"></div>
      <div class="beard_left">
        <div class="beard bread_1"></div>
        <div class="beard bread_2"></div>
        <div class="beard bread_3"></div>
      </div>
      <div class="beard_right">
        <div class="beard bread_1"></div>
        <div class="beard bread_2"></div>
        <div class="beard bread_3"></div>
      </div>
    </div>
    <div id="totoro_bottom">
      <div class="stomach">
        <div class="pattern"></div>
        <div class="pattern"></div>
        <div class="pattern"></div>
        <div class="pattern"></div>
        <div class="pattern"></div>
        <div class="pattern"></div>
      </div>
    </div>
    <div id="totoro_arms">
      <div class="arm arm_left"></div>
      <div class="arm arm_right"></div>
    </div>
    <div id="totoro_foot">
      <div class="foot foot_left"></div>
      <div class="foot foot_right"></div>
    </div>
    <div class="umbrella">
      <div class="inner">
        <div class="top">
          <div class="back"></div>
          <div class="part"></div>
          <div class="part"></div>
          <div class="part"></div>
        </div>
        <div class="handle"></div>
      </div>
    </div>
  </div>
  <div id="electric_light">
    <div class="pillar"></div>
  </div>
  <div id="bus_stop">
    <div id="circle"> 
      <p>七国山行</p>
      <div id="place">稲 荷 前</div>
    </div>
    <div id="hilt"></div>
    <div id="stand"></div>
  </div>
</div>
</template>
     
    <script>
    export default {
      name: 'Totoro',
      props: {
        backgroundColor: ''
      },
      
    }
           
    </script>
    

<style scoped lang="scss">
    $totoro_color: #4e4c3f;
    $light_color: #888679;

body {
  background-color: #081012;
  overflow: hidden;
  margin: 0;
  padding: 0;
}
#wrapper {
  width: 800px;
  height: 350px;
  margin: 100px auto 0 auto;
  position: relative;
}

#totoro {
  width: 300px;
  height: 300px;
  margin: 0 auto;
  position: relative;
  padding-top: 83px;
}

#electric_light {
  position: absolute;
  top: -280px;
  left: 0;
  perspective: 300px;
  .pillar {
    height: 440px;
    width: 50px;
    opacity: 0.5;
    background-color: #F7E485;
    transform: rotateX(30deg);
    box-shadow:0 0 50px 30px #F7E485;
  }
}

#bus_stop {
  position: absolute;
  width: 80px;
  height: 250px;
  top: 95px;
  left: -10px;
  #circle {
    position: relative;
    border-radius: 100%;
    width: 80px;
    height: 80px;
    background: linear-gradient(#88849b , #737277);
    overflow: hidden;
    border-top: solid 1px #d8cac1;
    p {
      color: #e2ddd9;
      position: absolute;
      top: -2px;
      left: 15px;
      font-size: 12px;
    }

    #place {
      margin-top: 29px;
      width: 80px;
      height: 25px;
      background-color: #d1d1cf;
      background: linear-gradient(#d1d1cf , #c7c7c3);
      text-align: center;
      color: #605f64;
      padding-top: 1px;
    }
  }
  #hilt {
    height: 150px;
    width: 3px;
    background-color: #9fa4a0;
    margin-left: 39px;
    position: relative;
    &:after {
      content: '';
      display: block;
      width: 30px;
      height: 50px;
      border-radius: 10%;
      left: -13px;
      top: 25px;
      position: absolute;
      border-top: solid 1px #d8cac1;
      background-color: #9fa4a0;
    }
  }
  #stand {
    height: 30px;
    width: 75px;
    background: linear-gradient(#9fa4a0 , #514c49);
    margin-left: 4px;
    border-top: solid 1px #d8cac1;
  }
}

#totoro_top {
  background-color: $totoro_color;
  width: 160px;
  height: 200px;
  margin: 0 auto;
  border-radius: 45%;
  position: relative;
  overflow: hidden;
  &:after {
   content:''; 
   background-color: $light-color;
   width: 160px;
   height: 160px;
   border-radius: 45%;
   position: absolute;
   top: 53px;
   left: -100px;
  }
}
#totoro_face {
  width: 160px;
  height: 200px;
  margin: 150px auto 0;
  border-radius: 45%;
  position: absolute;
  top: -70px;
  left: 70px;
}

#totoro_bottom {
  background-color: $totoro_color; 
  width: 210px;
  height: 210px;
  margin: -143px auto 0;
  border-radius: 48%;
  position: relative;
  z-index: 10;
  animation: respiration 2000ms ease-in-out infinite alternate;
  overflow: hidden;
  &:after {
    content: '';
    width: 180px;
    height: 190px;
    background-color: $light_color;
    border-radius: 100%;
    position: absolute;
    z-index: 1;
    top: 10px;
    left: -50px;
  }
}
.ear {
  width: 0;
  height: 0;
  border-top: 35px solid transparent;
  border-right: 13px solid transparent;
  border-bottom: 35px solid $totoro_color;
  border-left: 13px solid transparent;
  z-index: 30;
  position: absolute;
  top: -74px;
  &:after {
    content: '';
    width: 5px;
    height: 15px;
    background-color: $totoro-color;
    position: absolute;
    top: 34px;
    left: -2px;
  }
}
.left {
  left: 23px;
  transform: rotate(-15deg);  
}
.right {
  right: 25px;
  transform: rotate(15deg); 
}
.eye {
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background-color: #ffffff;
  position: absolute;
  z-index: 100;
  top: 20px;
  animation: eye_big 5000ms linear infinite alternate;
  &:before {
    content: '';
    width: 0px;
    height: 0px;
    border-radius: 50%;
    background-color: #ffffff;
    position: absolute;
    top: 7px;
    left: 9px;
    opacity: 0.6;
    z-index: 300;
    animation: light 5000ms linear infinite alternate;
  }

  @keyframes eye_big {
    0% {
      transform:scale(1);
    }
     70% {
      transform:scale(1);
    }
    100% {
     transform:scale(1.2);
    }
  }
  
  @keyframes light {
    0% {
      width: 0;
      height: 0;
    }
     70% {
      width: 0;
      height: 0;
    }
    100% {
      width: 5px;
      height: 5px;
    }
  }
  
  &:after {
    content: '';
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background-color: #000000;
    position: absolute;
    top: 6px;
    left: 6px;
    animation: pupil 5000ms linear infinite alternate;
  }
}
@keyframes pupil {
  from{
    transform: scale(1);
  }
  to{
    transform: scale(1.2);
  }
}

.left_eye{
  left: 33px;
}
.right_eye{
  right: 33px;
}
.nose {
  width: 20px;
  height: 10px;
  border-radius: 50%;
  background-color: #333333;
  position: absolute;
  top: 30px;
  left: 70px;
  z-index: 100;
}
.mouth {
  width: 98px;
  height: 25px;
  border-radius: 50%;
  border-bottom: solid 1px #333333;
  position: absolute;
  z-index: 200;
  top: 52px;
  background-color: #ffffff;
  left: 32px;
  animation: smile 5000ms 2000ms linear infinite alternate;
  &:after {
    content: '';
    display: block;
    position: absolute;
    width: 98px;
    height: 15px;
    top: -5px;
    left: 2px;
    background-color: $totoro-color;
    border-radius: 100%;
    z-index: 5;
    animation: smile2 5000ms 2000ms linear infinite alternate;
  }
}
@keyframes smile {
  0% {
    width: 12px;
    height: 10px;
    left: 75px;
    border-radius: 2%;
  }
  50% {
    width: 12px;
    height: 10px;
    left: 75px;
    border-radius: 2%;
  }
  70% {
    width: 98px;
    height: 25px;
    top: 50px;
    left: 32px;
    border-radius: 100%;
    border-bottom: solid 1px #292a1c;
  }
  100% {
    width: 98px;
    height: 25px;
    top: 50px;
    left: 32px;
    border-radius: 100%;
    border-bottom: solid 1px #292a1c;
  }
}
@keyframes smile2 {
  0% {
    width: 16px;
    height: 12px;
    left: -3px;
    top: -2px;
    border-radius: 2%;
  }
  50% {
    width: 16px;
    height: 12px;
    top: -2px;
    left: -3px;
    border-radius: 2%;
  }
  70% {
    width: 93px;
    height: 15px;
    top: -5px;
    left: 3px;
  }
  100% {
    width: 93px;
    height: 15px;
    top: -5px;
    left: 3px;
  }
}

.beard {
  width: 60px;
  height: 3px;
  position: absolute;
  border-top: solid 2px #333333;
  top: 50px;
  left: -25px;
  z-index: 300;
  border-radius: 50%; 
}
.bread_1 {
  transform:rotate(15deg);
  transform-origin: right bottom;
  top: 45px;
}
.bread_3 {
  transform: rotate(-15deg);
  transform-origin: right bottom;
  top: 55px;
}
.beard_right {
  position: absolute;
  right: 5px;
  .bread_1 {
    transform: rotate(-15deg);
    transform-origin: left bottom;    
  }
  .bread_3 {
    transform: rotate(15deg);
    transform-origin: left bottom;    
  }
}

.stomach {
  position: absolute;
  top: 30px;
  left: 24px;
  width: 160px;
  height: 160px;
  background-color: #bfad83;
  border-radius: 45% 45% 45% 45%;
  z-index: 10;
  overflow: hidden;
  &:after {
    content:'';
    position: absolute;
    top: -50px;
    left: -150px;
    width: 240px;
    height: 240px;
    background-color: #ffffff;
    border-radius: 45% 45% 45% 45%;
    z-index: 5;
    opacity: 0.3;
  }
}

@keyframes respiration {
  0% {
    transform:scale(1.0);
  }
  100% {
    transform:scale(1.05);
  }
}

.pattern {
  width: 10px;
  height: 10px;
  border-top: solid 5px $totoro-color;
  border-left: solid 5px $totoro-color;
  border-bottom: solid 5px #bfad83;
  border-right: solid 5px #bfad83;
  position: absolute;
  top: 25px;
  left: 30px;
  transform: rotate(45deg);
}

.pattern:nth-child(2) {
  left: 70px;
  top: 20px;
}
.pattern:nth-child(3) {
  left: 110px;
}
.pattern:nth-child(4) {
  top: 50px;
  left: 30px;
}
.pattern:nth-child(5) {
  top: 50px;
  left: 70px;
}
.pattern:nth-child(6) {
  top: 50px;
  left: 110px;
}

#totoro_arms {
  overflow: hidden;
  .arm {
    background-color: $totoro-color;
    width: 100px;
    height: 140px;
    position: absolute;
    top: 175px;
    left: 35px;
    border-radius: 50%;
  }
  .arm_left {
    transform: rotate(10deg);
    transform-origin: right top;
    background-color: $light_color;
    z-index: 1;
  }
  .arm_right {
    width: 50px;
    height: 100px;
    transform: rotate(-60deg);
    transform-origin: left top;
    top: 200px;
    left: 145px;
    z-index: 300;
    border-radius: 50% 50% 50% 0;
  }
}

#totoro_foot {
  width: 200px;
  margin: 0 auto;
  position: relative;
  .foot {
    background: linear-gradient($totoro-color 55%, transparent 55%);
    width: 50px;
    height: 18px;
    border-radius: 50%;
    position: absolute;
    z-index: 5;
  }
  .foot_left {
    top: -10px;
    left: 40px;
  }
  .foot_right {
    top: -10px;
    left: 115px;
  }
}

.umbrella{
  position: absolute;
  top: -10px;
  left: 60px;
  .inner {
    position: relative;
    width: 200px;
    margin: 0 auto;
    .back {
      width: 300px;
      height: 100px;
      border-radius: 50%;
      position: absolute;
      top: -16px;
      left: -50px;
      background:  #06171e;
      background: linear-gradient(transparent 78%, #081012 35%);
    }

    .top {
      width: 200px;
      height: 130px;
      border-radius: 50%;
      position: relative;
      overflow: hidden;
      box-shadow: 0 -10px 20px -3px rgba(255,255,255,0.5);
      background: linear-gradient(#4e567b 55%, transparent 55%);
      &:after {
        content: '';
        width: 200px;
        height: 100px;
        border-radius: 50%;
        position: absolute;
        left: 61px;
        top: -9px;
        background: linear-gradient(#12293b 70%, transparent 55%);
      }
      .part {
        width: 67px;
        height: 50px;
        border-radius: 50%;
        background: linear-gradient(#081012 55%, transparent 55%);
        position: absolute;
        top: 37px;
        z-index: 10;
        &:nth-child(2) {
          left: 67px;
        }
        &:nth-child(3) {
          right: 0;
        }
      }
    }
    .handle {
      width: 3px;
      height: 150px;
      background-color: #3c3c43;
      position: absolute;
      top: 36.5px;
      left: 105px;
      z-index: 200;
      &:after {
        content: '';
        width: 15px;
        height: 28px;
        border-style: none solid solid solid;
        border-width: 7px;
        border-color: #23251c;
        border-radius: 0 0 0 100%;
        position: absolute;
        top: 140px;
        left: -24px;
      }
    }
  }
}

#ground {
  width: 100%;
  height: 500px;
  background: linear-gradient(to right, #1d2110 0%,#041c03 100%);
  overflow: hidden;
  position: relative;
  box-shadow: 0 -10px 25px -3px rgba(255,255,255,0.4);
}
.totoro_shadow {
  width: 300px;
  margin: 0 auto;
  position: relative;
  .inner {
    width: 300px;
    height: 30px;
    background-color: #050000;
    border-radius: 100%;
    position: absolute;
    left: 120px;
    top: -5px;
    transform: skewX(-100deg);
  }
}
</style>