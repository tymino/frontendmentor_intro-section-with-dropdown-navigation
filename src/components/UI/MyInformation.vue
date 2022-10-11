<template>
  <div class="information">
    <h1 class="information__title">{{ title }}</h1>
    <p class="information__describe">{{ describe }}</p>

    <my-button class="information__button">{{ buttonText }}</my-button>

    <ul class="information__client-list">
      <li class="information__client-item" v-for="icon in clientIcons" :key="icon">
        <my-icon :iconName="icon" />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'my-information',
  data() {
    return {
      title: 'Make remote work',
      describe:
        'Get your team in sync, no matter your location. Streamline processes create team rituals, and watch productivity soar.',
      buttonText: 'Learn more',
      clientIcons: [
        'client-databiz.svg',
        'client-audiophile.svg',
        'client-meet.svg',
        'client-maker.svg',
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.information {
  display: flex;
  flex-direction: column;
  margin: auto;
  max-width: 494px;
}
.information__title {
  margin-bottom: 60px;
  font-size: 4.6rem;
  color: var(--color-black);
  text-align: left;
}
.information__describe {
  margin-bottom: 50px;
  font-size: 1.2rem;
  color: var(--color-gray);
  text-align: left;
}
.information__button {
  align-self: flex-start;
  margin-bottom: 80px;
}
.information__client-list {
  display: flex;
  list-style: none;
}
.information__client-item:not(:last-child) {
  margin-right: 20px;
}
</style>
