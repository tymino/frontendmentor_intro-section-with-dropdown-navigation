<!-- eslint-disable vuejs-accessibility/click-events-have-key-events -->
<template>
  <div class="dropdown" @click="toggleDropMenu">
    <p class="dropdown__title">{{ data.title }}</p>
    <my-svg class="dropdown__arrow" :svgName="`icon-arrow-${isOpen ? 'up' : 'down'}.svg`" />
    <div class="dropdown__list" v-show="isOpen">
      <my-link
        v-for="link in data.linkList"
        :key="link.id"
        :linkName="link.name"
        :svgName="link.svgName"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'my-dropdown',
  data() {
    return {
      isOpen: true,
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
  max-width: 100px;
}
.dropdown__arrow {
  margin-left: 6px;
}
.dropdown__list {
  position: absolute;
  top: 100%;
  right: 0;
  background: rgb(151, 151, 151);
}
</style>
