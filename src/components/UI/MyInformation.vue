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
  width: 494px;
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

@media (max-width: 1000px) {
  .information {
    max-width: 494px;
    margin-top: 80px;
  }
  .information__title {
    margin-bottom: 30px;
    font-size: 3.2rem;
    text-align: center;
  }
  .information__describe {
    margin-bottom: 30px;
    font-size: 1.2rem;
    text-align: center;
  }
  .information__button {
    align-self: center;
    margin-bottom: 40px;
  }
  .information__client-list {
    justify-content: center;
  }
}
@media (max-width: 525px) {
  .information {
    width: 100%;
    margin-top: 40px;
  }
  .information__title {
    margin-bottom: 20px;
    font-size: 2.2rem;
    text-align: center;
  }
  .information__describe {
    margin-bottom: 20px;
    font-size: 1rem;
    text-align: center;
  }
  .information__button {
    align-self: center;
    margin-bottom: 40px;
  }
  .information__client-list {
    justify-content: center;
    flex-wrap: wrap;
  }
  .information__client-item:not(:last-child) {
    margin-right: 16px;
    margin-bottom: 12px;
  }
}
</style>
