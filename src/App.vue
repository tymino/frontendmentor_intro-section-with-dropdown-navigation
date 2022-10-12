<template>
  <div class="main">
    <c-navbar />
    <c-content />
    <div class="attribution">
      Challenge by
      <a
        href="https://www.frontendmentor.io/challenges/intro-section-with-dropdown-navigation-ryaPetHE5"
        target="_blank"
        >Frontend Mentor</a
      >. Coded by <a href="https://github.com/tymino">tymino</a>.
    </div>
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

<style lang="scss">
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
  position: relative;
  text-align: center;
  padding: 30px;
}

.main {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.attribution {
  position: absolute;
  top: 6px;
  left: 6px;
  font-size: 0.7rem;
  color: var(--color-black);
  opacity: .6;

  a {
    color: var(--color-gray);

    &:hover {
      color: var(--color-black);
    }
  }
}
</style>
