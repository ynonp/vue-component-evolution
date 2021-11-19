<script setup>
import { ref, reactive, onMounted, onUnmounted } from 'vue';

const props = defineProps({
  start: Number,
  step: Number,
});

const data = reactive({ value: props.start });
function inc() {
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

</script>

<template>
  <div>
    <button @click="inc">{{data.value}}</button>
  </div>
</template>
