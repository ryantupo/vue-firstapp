<template>
    <div>
    {{ timerCount }}
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
      this.remainingMinutes = this.reminderAfterHours % 60;
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
      remainingMinutes: 0
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
            console.log("Seconds Left :", this.remainingMinutes);
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
</style>
