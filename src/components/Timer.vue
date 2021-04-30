<template>
  <v-container class="w-100">
    <div class="text-center Time" v-if="currentTime">
      {{ minutes | formatTime }} : {{ seconds | formatTime }}
    </div>
    <div class="text-center" v-if="!currentTime">
      Time's Up!
    </div>
  </v-container>
</template>

<script>
import moment from 'moment'

export default {
  data() {
    return {
      speed: 1000,
      deadline: moment(new Date()).add(10, 'minute').format(),
      currentTime: Date.parse(this.deadline) - Date.parse(new Date()),
    };
  },
  mounted() {
    setTimeout(this.countdown, 0);
  },
  computed: {
    seconds() {
      return Math.floor((this.currentTime / 1000) % 60);
    },
    minutes() {
      return Math.floor((this.currentTime / 1000 / 60) % 60);
    },
    hours() {
      return Math.floor((this.currentTime / (1000 * 60 * 60)) % 24);
    },
    days() {
      return Math.floor(this.currentTime / (1000 * 60 * 60 * 24));
    }
  },
  filters: {
    formatTime(value) {
      if (value < 10) {
        return "0" + value;
      }
      return value;
    }
  },
  methods: {
    countdown() {
        this.currentTime = Date.parse(this.deadline) - Date.parse(new Date());
        if (this.currentTime > 0) {
          setTimeout(this.countdown, this.speed);
        } else {
          this.currentTime = null;
        }
    }
  }
}
</script>

<style scoped>
.Time{
  font-size: 2em;
  color: #ffffff;
  font-family: "Digit";
}
</style>