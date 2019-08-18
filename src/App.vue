<template>
  <div id="app">
    <EmiCalculator/>
  </div>
</template>

<script>
import EmiCalculator from './components/EmiCalculator.vue';

export default {
  name: 'app',
  components: {
    EmiCalculator,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
