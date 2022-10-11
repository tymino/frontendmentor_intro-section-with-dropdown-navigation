<template>
  <div class="main">
    <c-navbar />
    <c-content />
  </div>
</template>

<script>
import CNavbar from '@/components/Navbar.vue';
import CContent from '@/components/Content.vue';

export default {
  components: {
    CNavbar,
    CContent,
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
  background: var(--color-white);
}
#app {
  text-align: center;
  padding: 30px;
}

.main {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
</style>
