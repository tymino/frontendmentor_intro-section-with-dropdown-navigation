<template>
  <img :src="`./images/${svgName}.svg`" alt="1" />
</template>

<script>
export default {
  name: 'my-svg',
  props: {
    svgName: {
      type: String,
      default: '',
    },
  },
};
</script>

<style scoped></style>
