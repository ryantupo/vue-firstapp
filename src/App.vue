<template>
<div>
    <h1>Timers</h1>
  <Button @btn-clicked="sayhi" :text="'heyy'" :color="'green'"/>
  <Countdown :totalTime=4535623 />
</div>

</template>

<script>
import Button from "./components/Button";
import Countdown from './components/Coutdown'

export default {
  name: "App",
  components: {
    Button,
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
