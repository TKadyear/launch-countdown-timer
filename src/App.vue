<script setup>
import CountdownTimer from './components/CountdownTimer.vue'
</script>
<template>
  <CountdownTimer />
  <div id="hills" alt=" "></div>
</template>

<style>
body {
  margin: 0;
  height: 100vh;
  background: url(/images/bg-stars.svg), linear-gradient(#1e1e28, #30243a);
}
#hills {
  background: url(/images/pattern-hills.svg) right;
  background-size: cover;
  width: 100%;
  height: 25vh;
  /* height: 197px; */
  position: fixed;
  bottom: 0;
}
@media screen(min-width: 978px) {
  #hills {
    height: 197px;
  }
}
</style>
