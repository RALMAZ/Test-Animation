<template>
  <div class="tech-block">
    <p class="tech-blue">Working with</p>
    <p class="tech-blue">DAX30 companies</p>
    <p class="tech-orange">Featured multiple times</p>
    <p class="tech-orange">on Apple's appstore</p>
    <p class="tech-blue">award winning apps</p>
    <br/>
    <p class="tech-black">{ Technologies:</p>
    <p class="tech-orange">Ionic, react, angular, java,</p>
    <p class="tech-orange">kotlin, swift, objective c,</p>
    <p class="tech-orange">python, ruby, .net,</p>
    <p class="tech-orange">node, scala,</p>
    <p class="tech-blue">CI, CD, automated testing,</p>
    <p class="tech-orange">kubernetes, docker,</p>
    <p class="tech-orange">AWS, Azure <span class="tech-black">}</span></p>
  </div>
</template>

<script>
export default {
  
}
</script>

<style>
  .tech-block {
    position: absolute;
    top: 100px;
    right: 80px;
    bottom: 0;
    z-index: 100;
    width: 280px;
    height: 410px;
    background-color: white;
    padding: 20px 25px;
    text-transform: uppercase;
    font-size: 16px;
    line-height: 0.8;
  }

  .tech-black {
    color: black;
  }

  .tech-blue {
    color: #0200FF;
  }

  .tech-orange {
    color: rgb(243, 94, 40);
  }
</style>