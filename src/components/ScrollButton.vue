<template>
  <div class="scroll-downs">
    <div class="mousey">
      <div class="scroller"></div>
    </div>
  </div>
</template>

<script>
export default {
  
}
</script>

<style>
  .scroll-downs {
    position: absolute;
    top: 335px;
    right: 0;
    bottom: 0;
    left: 135px;
    z-index: 100;
    width :34px;
    height: 55px;
  }

  .mousey {
    width: 3px;
    padding: 10px 15px;
    height: 35px;
    border: 2px solid #fff;
    border-radius: 25px;
    opacity: 0.75;
    box-sizing: content-box;
  }

  .scroller {
    width: 3px;
    height: 10px;
    border-radius: 25%;
    background-color: #fff;
    animation-name: scroll;
    animation-duration: 1.2s;
    animation-timing-function: cubic-bezier(.15,.41,.69,.94);
    animation-iteration-count: infinite;
  }

  @keyframes scroll {
    10% { transform: translateY(2px); opacity: 1; }
    20% { transform: translateY(2px); opacity: 1; }
    30% { transform: translateY(2px); opacity: 1; }
    40% { transform: translateY(2px); opacity: 1; }
    50% { transform: translateY(0); opacity: 1; }
    60% { transform: translateY(-2px); opacity: 1; }
    70% { transform: translateY(-2px); opacity: 1; }
    80% { transform: translateY(-2px); opacity: 1; }
    90% { transform: translateY(-2px); opacity: 1; }
  }
</style>