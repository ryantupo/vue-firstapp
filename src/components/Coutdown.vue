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
  data() {
    return {
      timerCount: this.totalTime,
      amountOfDays: this.totalTime % 86400,
      reminderAfterDays: Math.floor(this.totalTime / 86400),
      amountOfHours: this.reminderAfterDays % 3600,
      reminderAfterHours: this.reminderAfterDays / 3600,
      amountOfMinutes: this.reminderAfterHours % 60,
      remainingMinutes: this.reminderAfterHours / 60,
    };
  },

  watch: {
    timerCount: {
      handler(value) {
        if (value > 0) {
          setTimeout(() => {
            this.timerCount--;
            console.log(this.timerCount);
            console.log(this.reminderAfterDays)
            console.log("days left :", this.amountOfDays);
            console.log("Hours Left :" , this.amountOfHours);
            console.log("minutes Left :", this.amountOfMinutes);
            console.log("Seconds Left :" , this.remainingMinutes);
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
