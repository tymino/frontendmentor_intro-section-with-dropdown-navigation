<template>
  <img :class="{ cube: isCube }" :src="`./images/${svgName}`" :alt="svgName.replace(/.svg/, '')" />
</template>

<script>
export default {
  name: 'my-svg',
  props: {
    svgName: {
      type: String,
      default: '',
    },
    isCube: {
      type: Boolean,
      default: true,
    },
  },
};
</script>

<style scoped>
.cube {
  width: 16px;
  height: 16px;
}
</style>
