<template>
  <img
    :class="{ cube: isCube }"
    :src="`./images/${iconName}`"
    :alt="iconName.replace(/.svg/, '')"
  />
</template>

<script>
export default {
  name: 'my-icon',
  props: {
    iconName: {
      type: String,
      default: '',
    },
    isCube: {
      type: Boolean,
      default: false,
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
