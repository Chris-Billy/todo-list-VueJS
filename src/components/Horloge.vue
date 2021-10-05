<template>
  <div>{{ hours }} : {{ mins }} : {{ secs }}</div>
</template>

<script>
export default {
  name: "Horloge",
  data() {
    return {
      now: new Date(),
      intervalID: null
    };
  },
  computed: {
    hours() {
      return this.now.getHours();
    },
    mins() {
      return this.now.getMinutes() < 10
        ? `0${this.now.getMinutes()}`
        : this.now.getMinutes();
    },
    secs() {
      return this.now.getSeconds() < 10
        ? `0${this.now.getSeconds()}`
        : this.now.getSeconds();
    },
  },
  beforeMount() {
    this.intervalID = setInterval(() => {
        this.now = new Date()
    });
  },
  beforeDestroy() {
      clearInterval(this.intervalID)
  },
};
</script>
