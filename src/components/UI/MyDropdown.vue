<!-- eslint-disable vuejs-accessibility/click-events-have-key-events -->
<template>
  <div class="dropdown" @click="toggleDropMenu">
    <p class="dropdown__title">{{ data.title }}</p>
    <my-icon
      class="dropdown__arrow"
      :isCube="false"
      :iconName="`icon-arrow-${isOpen ? 'up' : 'down'}.svg`"
    />
    <div class="dropdown__list" v-show="isOpen" :style="`${data.sidePos}: 0;`">
      <my-link
        v-for="link in data.linkList"
        :key="link.id"
        :linkName="link.name"
        :iconName="link.iconName"
        style="margin-bottom: 16px"
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
  methods: {
    toggleDropMenu() {
      this.isOpen = !this.isOpen;
    },
  },
};
</script>

<style scoped>
.dropdown {
  position: relative;
  display: flex;
  align-items: center;
  user-select: none;
}
.dropdown__title {
  margin: 0;
  text-transform: capitalize;
}
.dropdown__arrow {
  margin-left: 6px;
}
.dropdown__list {
  position: absolute;
  top: 90%;
  padding: 20px 20px 4px 20px;
  border-radius: 10px;
  box-shadow: 0px 2px 6px 0px var(--color-gray);
}
</style>
