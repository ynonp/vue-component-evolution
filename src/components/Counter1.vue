<script>
export default {
  data() {
    return {
      value: this.start,
    }
  },

  props: {
    start: Number,
    step: Number,
  },

  methods: {
    inc() {
      this.value += this.step;
    }
  },

  mounted() {
    this.timer = setInterval(() => {
      this.value -= 1;
    }, 1000);
  },

  unmounted() {
    clearInterval(this.timer);
  }

};
</script>

<template>
  <div>
    <button @click="inc">{{value}}</button>
  </div>
</template>

<style scoped>
</style>
