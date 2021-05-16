<template>
<div>
    <h1>Timers</h1>
    
  <div><Countdown class="sizingLarge" :totalTime=4535623 /></div>

</div>

</template>

<script>
import Countdown from "./components/Coutdown";

export default {
  name: "App",
  components: {
    Countdown
  },
  methods: {
    sayhi() {
      console.log("heyyyyyyyyyy");
    }
  },
  data() {
    return {
      timers: []
    };
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

.sizingSmall {
  zoom: 0.5;
  -moz-transform: scale(0.5);
}
.sizingMedium {
  zoom: 0.75;
  -moz-transform: scale(0.75);
}
.sizingLarge {
  zoom: 0.9;
  -moz-transform: scale(0.9);
}
</style>
