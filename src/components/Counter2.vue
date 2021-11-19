<script>
import { ref, reactive, onMounted, onUnmounted } from 'vue';

export default {
  props: {
    start: Number,
    step: Number,
  },
  setup(props) {
    const data = reactive({ value: props.start });
    const inc = function() {
      console.log(data);
      data.value += props.step;
    }
    let timer;

    onMounted(() => {
      timer = setInterval(() => {
        data.value -= 1;
      }, 1000);
    });

    onUnmounted(() => {
      clearInterval(timer);
    });

    return {
      data,
      inc,
    };
  }
};
</script>

<template>
  <div>
    <button @click="inc">{{data.value}}</button>
  </div>
</template>
