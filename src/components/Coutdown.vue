<template>
    <div class="">
    <div class="padding mainBlock">
    <div style="margin-right:50px;" class="padding numberBlock">
    <p>{{ this.amountOfDays }}</p>
    </div>
        <div style="margin-right:50px;" class="padding numberBlock">
    <p>{{ this.amountOfHours }}</p>
    </div>
        <div style="margin-right:50px;" class="padding numberBlock">
    <p>{{ this.amountOfMinutes }}</p>
    </div>
        <div class="padding numberBlock">
    <p>{{ this.remainingSeconds }}</p>
    </div>
    
    </div>
    
    </div>
</template>

<script>
export default {
  name: "CountDown",
  props: {
    totalTime: Number
  },
  methods: {
    upDate() {
      this.amountOfDays = Math.floor(this.timerCount / 86400);
      this.reminderAfterDays = this.timerCount % 86400;
      this.amountOfHours = Math.floor(this.reminderAfterDays / 3600);
      this.reminderAfterHours = this.reminderAfterDays % 3600;
      this.amountOfMinutes = Math.floor(this.reminderAfterHours / 60);
      this.remainingSeconds = this.reminderAfterHours % 60;
    }
  },
  data() {
    return {
      timerCount: this.totalTime,
      amountOfDays: 0,
      reminderAfterDays: 0,
      amountOfHours: 0,
      reminderAfterHours: 0,
      amountOfMinutes: 0,
      remainingSeconds: 0
    };
  },

  watch: {
    timerCount: {
      handler(value) {
        if (value > 0) {
          setTimeout(() => {
            this.timerCount--;
            this.upDate();
            console.log(this.timerCount);
            console.log(this.reminderAfterDays);
            console.log("days left :", this.amountOfDays);
            console.log("Hours Left :", this.amountOfHours);
            console.log("minutes Left :", this.amountOfMinutes);
            console.log("Seconds Left :", this.remainingSeconds);
          }, 1000);
        } else if (value === 0) {
          console.log("finished");
        }
      },
      immediate: true // This ensures the watcher is triggered upon creation
    }
  }
};
</script>

<style>
.numberBlock {
  
  vertical-align: middle;
  text-align: center;
  width: 50px;
  height: 50px;
  background: linear-gradient(#e66465, #9198e5);
  box-shadow: 0 8px 6px -6px black;
}

.mainBlock {
  margin-top:50px;
  display: flex;
  flex-wrap: wrap;
  margin: auto;
  width: 400px;
  padding: 50px;
  margin-bottom: 50px;
}

.padding {
  background: linear-gradient(#e66465, #9198e5);
  border-style: solid;
  border-width: 5px 5px;
  box-shadow: 0 8px 6px -6px black;
}

.center{
  position:absolute;
  top:50%;
  left:50%;

}
</style>
