<template>
  <MySvg />
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';
import MySvg from './components/UI/MySvg.vue';

export default {
  name: 'App',
  components: {
    MySvg,
  },
};
</script>

<style>
#app {
  font-family: 'Epilogue', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
