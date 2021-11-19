<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import { ref } from 'vue';
import Counter1 from './components/Counter1.vue';
import Counter2 from './components/Counter2.vue';
import Counter3 from './components/Counter3.vue';

const showCounter1 = ref(true);
const showCounter2 = ref(true);
const showCounter3 = ref(true);

</script>

<template>
  <h1>Counter 1</h1>
  <input type="checkbox" v-model="showCounter1" />
  <Counter1 v-if="showCounter1" :start="5" :step="2" />

  <h1>Counter 2</h1>
  <input type="checkbox" v-model="showCounter2" />
  <Counter2 v-if="showCounter2" :start="5" :step="2" />

  <h1>Counter 3</h1>
  <input type="checkbox" v-model="showCounter3" />
  <Counter3 v-if="showCounter3" :start="5" :step="2" />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
