<script>
import PanelTimer from "./PanelTimer.vue"
export default {
  data() {
    return {
      msg: "We're launching soon",
      day: 0,
      hours: 0,
      minutes: 0,
      seconds: 0,
      releaseDate: this.release()
    };
  },
  mounted() {
    setInterval(() => this.setTime(), 1000)
  },
  methods: {
    release() {
      const year = new Date().getFullYear();
      const month = new Date().getMonth();
      const day = new Date().getDate() + 9;
      return new Date(year, month, day, 17, 30, 0);
    },
    padZero(number) {
      return `${number}`.padStart(2, 0);
    },
    setTime() {
      const Today = new Date();
      const distance = (this.releaseDate.getTime() - Today.getTime());
      // console.log(Countdown)
      const day = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);
      // TODO Some dates are negative
      this.day = `${day}`.padStart(2, 0);
      this.hours = `${hours}`.padStart(2, 0);
      this.minutes = `${minutes}`.padStart(2, 0);
      this.seconds = `${seconds}`.padStart(2, 0);
    }
  },
  components: { PanelTimer }
}
</script>

<template>
  <div class="container">
    <h1>{{ msg }}</h1>
    <div class="container-panel">
      <PanelTimer>{{ day }}</PanelTimer>
      <PanelTimer>{{ hours }}</PanelTimer>
      <PanelTimer>{{ minutes }}</PanelTimer>
      <PanelTimer>{{ seconds }}</PanelTimer>
    </div>
  </div>
</template>

<style scoped>
h1 {
  color: white;
  font-family: sans-serif;
  font-variant-caps: all-small-caps;
  text-align: center;
}
a {
  color: #42b983;
}
img {
  /* object-fit: fill; */
}
.container-panel {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 10px;
}
</style>
