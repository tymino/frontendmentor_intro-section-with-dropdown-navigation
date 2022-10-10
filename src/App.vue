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
  --font-size: 16px;
  --font-family: 'Epilogue', sans-serif;

  --border-radius: 14px;

  --color-white: hsl(0, 0%, 98%);
  --color-gray: hsl(0, 0%, 41%);
  --color-black: hsl(0, 0%, 8%);
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
html {
  font-family: var(--font-family);
}
#app {
  text-align: center;
  padding: 30px;
}

.main {
  display: flex;
  justify-content: center;
}
</style>
