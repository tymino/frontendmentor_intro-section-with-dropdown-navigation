<!-- eslint-disable vuejs-accessibility/click-events-have-key-events -->
<template>
  <div class="dropdown" @click="clickInElement">
    <div class="dropdown__header">
      <p class="dropdown__title">{{ data.title }}</p>
      <my-icon
        class="dropdown__arrow"
        :isCube="false"
        :iconName="`icon-arrow-${isOpen ? 'up' : 'down'}.svg`"
      />
    </div>
    <div class="dropdown__list" v-show="isOpen" :style="`${data.sidePos}: 0;`" @click.stop>
      <my-link
        class="dropdown__link"
        v-for="link in data.linkList"
        :key="link.id"
        :linkName="link.name"
        :iconName="link.iconName"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'my-dropdown',
  data() {
    return {
      isOpen: false,
    };
  },
  props: {
    data: {
      type: Object,
      default: () => {},
    },
  },
  created() {
    window.addEventListener('click', this.outsideClick);
  },
  beforeUnmount() {
    window.removeEventListener('click', this.outsideClick);
  },
  methods: {
    toggleDropMenu() {
      this.isOpen = !this.isOpen;
    },
    close() {
      this.isOpen = false;
    },
    outsideClick(event) {
      if (!this.$el.contains(event.target)) {
        this.close();
      }
      if (this.$el.contains(event.target)) this.toggleDropMenu();
    },
  },
};
</script>

<style lang="scss" scoped>
.dropdown {
  position: relative;
  user-select: none;
  cursor: pointer;

  &:hover .dropdown__title {
    color: var(--color-black);
  }
}
.dropdown__header {
  display: flex;
  align-items: center;
}
.dropdown__title {
  margin: 0;
  color: var(--color-gray);
  text-transform: capitalize;
}
.dropdown__arrow {
  margin-left: 6px;
}
.dropdown__list {
  position: absolute;
  top: 40px;
  padding: 26px;
  border-radius: var(--border-radius);
  box-shadow: 0px 2px 6px 0px var(--color-gray);

  .dropdown__link:not(:last-child) {
    margin-bottom: 20px;
  }
}

@media (max-width: 900px) {
  .dropdown {
  }
  .dropdown__header {
  }
  .dropdown__title {
  }
  .dropdown__arrow {
  }
  .dropdown__list {
    position: static;
    top: 0;
    /* padding-bottom: 10px; */
    border-radius: none;
    box-shadow: none;
  }
}
</style>
