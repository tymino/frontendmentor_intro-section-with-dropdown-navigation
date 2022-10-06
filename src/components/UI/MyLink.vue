<template>
  <a :href="linkHref" class="link">
    <my-svg class="link__icon" v-if="svgName.length != ''" :svgName="svgName" />
    <p class="link__text">{{ linkName }}</p>
  </a>
</template>

<script>
export default {
  name: 'my-link',
  props: {
    linkName: {
      type: String,
      default: 'link',
    },
    linkHref: {
      type: String,
      default: '#',
    },
    svgName: {
      type: String,
      default: '',
    },
  },
};
</script>

<style scoped>
.link {
  display: flex;
  align-items: center;
  text-decoration: none;
}
.link:hover > .link__text {
  color: var(--color-black);
}
.link__icon {
  margin-right: 12px;
}
.link__text {
  margin: 0;
  color: var(--color-gray);
  white-space: nowrap;
  text-transform: capitalize;
}
</style>
