<template>
  <img :src="`./images/${svgName}`" :alt="svgName.replace(/.svg/, '')" />
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
