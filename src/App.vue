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
  /* background-position: rigth; */
  width: 100%;
  height: 20vh;
  position: fixed;
  bottom: 0;
}
</style>
