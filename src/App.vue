<template>
<div>
    <h1>Timers</h1>
  <Countdown :totalTime=4535623 />
</div>

</template>

<script>

import Countdown from './components/Coutdown'

export default {
  name: "App",
  components: {
    Countdown
  },
  methods: {
    sayhi() {
      console.log("heyyyyyyyyyy");
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.btn {
  width: 50px;
  height: 50px;
}
</style>
