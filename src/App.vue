<template>
  <div class="main">
    <navbar />
  </div>
</template>

<script>
import Navbar from '@/components/Navbar.vue';

export default {
  components: {
    Navbar,
  },
};
</script>

<style>
:root {
  --color-white: hsl(0, 0%, 98%);
  --color-gray: hsl(0, 0%, 41%);
  --color-black: hsl(0, 0%, 8%);
}
#app {
  font-family: 'Epilogue', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  padding: 20px;
}

.main {
  display: flex;
  justify-content: center;
}
</style>
