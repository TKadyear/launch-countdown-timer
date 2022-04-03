<script></script>
<template>
  <div class="panel">
    <div class="panel-text">
      <slot></slot>
    </div>
    <div class="panel-top"></div>
    <div class="panel-bottom"></div>
    <div class="circle circle-left"></div>
    <div class="circle circle-right"></div>
  </div>
  <!-- <slot type="text"></slot> -->
</template>
<style scoped>
.panel {
  width: 50px;
  height: 50px;
  position: relative;

  border-radius: 6px;
  box-shadow: 0 4px 2px #1a1823;
}
.panel-text {
  font-weight: bold;
  font-size: 28px;
  color: #f76485;
  width: 100%;
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  text-align: center;
  z-index: 1;
}
.panel-top,
.panel-bottom {
  position: absolute;
  height: 50%;
  width: 100%;
  border-radius: inherit;
}
.panel-top {
  background: #252538;
  top: 0;
}
.panel-bottom {
  background: #2f2f48;
  bottom: 0;
}
.panel::after {
  content: "";
  position: absolute;
  width: 100%;
  top: 50%;
  z-index: 2;
  transform: translateY(-50%);
  border: 2px inset #2c2c445a;
  border-top-width: 1px;
  border-bottom-color: #766b791f;
  border-left: 0px;
  border-right: 0px;
}
.circle {
  position: absolute;
  width: 5px;
  height: 5px;
  top: 50%;
  transform: translateY(-50%);
  background: #0d0c11;
  border-radius: 50%;
}
.circle-left {
  left: -2.75px;
  clip-path: polygon(50% 0, 100% 0, 100% 100%, 50% 100%);
}
.circle-right {
  right: -2.75px;
  clip-path: polygon(0 0, 50% 0, 50% 100%, 0% 100%);
}
</style>
