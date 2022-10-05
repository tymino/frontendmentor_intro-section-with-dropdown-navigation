<template>{{ linkName }}</template>

<script>
export default {
  name: 'my-link',
  props: {
    linkName: {
      type: String,
      default: 'link',
      required: true,
    },
    hasSvg: {
      type: Boolean,
      default: false,
    },
    svgName: {
      type: String,
      default: '',
    },
  },
};
</script>

<style scoped></style>
