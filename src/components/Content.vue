<template>
  <div class="content">
    <my-information />
    <picture class="content__picture">
      <source srcset="/images/image-hero-desktop.png" media="(min-width: 800px)" />
      <img class="content__image" src="/images/image-hero-mobile.png" alt="hero" />
    </picture>
  </div>
</template>

<script>
export default {
  name: 'c-content',
};
</script>

<style lang="scss" scoped>
.content {
  display: flex;
  justify-items: center;
  align-items: center;
  margin: 80px 110px;

  padding: 0;
}
.content__picture {
  margin-left: 120px;
}
.content__image {
  max-width: 530px;
  max-height: 706px;
}
</style>
