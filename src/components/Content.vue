<template>
  <div class="content">
    <my-information />
    <picture class="content__picture">
      <source srcset="/images/image-hero-desktop.png" media="(min-width: 1000px)" />
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
  margin: 80px auto;

  padding: 0;
}
.content__picture {
  margin-left: 120px;
}
.content__image {
  max-width: 530px;
  max-height: 706px;
}

@media (max-width: 1280px) {
  .content__picture {
    margin-left: 40px;
  }
  .content__image {
    max-width: 436px;
    max-height: 581px;
  }
}
@media (max-width: 1000px) {
  .content {
    flex-direction: column-reverse;
  }
  .content__picture {
    margin-left: 0px;
  }
  .content__image {
    max-width: 100%;
    height: auto;
  }
}
</style>
