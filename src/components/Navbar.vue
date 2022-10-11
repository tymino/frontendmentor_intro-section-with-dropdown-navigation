<template>
  <div class="navbar">
    <div
      class="navbar__background-burger"
      v-if="isOpenBurger"
      @click="closeBurgerMenu"
      @keypress="closeBurgerMenu"
    ></div>
    <my-icon class="navbar__logo" iconName="logo.svg" />
    <my-icon class="navbar__burger-menu" iconName="icon-menu.svg" @click="openBurgerMenu" />
    <div class="navbar__wrapper" :class="{ 'navbar__wrapper--open': isOpenBurger }">
      <my-icon
        class="navbar__burger-close"
        iconName="icon-close-menu.svg"
        @click="closeBurgerMenu"
      />
      <div class="navbar__link-container">
        <my-dropdown
          class="navbar__link"
          v-for="data in dropdownData"
          :key="data.id"
          :data="data"
        />
        <my-link class="navbar__link" linkName="careers" />
        <my-link class="navbar__link" linkName="About" />
      </div>
      <div class="navbar__button-container">
        <my-button class="navbar__button" buttonType="secondary">login</my-button>
        <my-button class="navbar__button" buttonType="primary">register</my-button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'c-navbar',
  data() {
    return {
      isOpenBurger: false,
      dropdownData: [
        {
          id: 0,
          title: 'features',
          sidePos: 'right',
          linkList: [
            { id: '001', name: 'todo list', iconName: 'icon-todo.svg' },
            { id: '002', name: 'calendar', iconName: 'icon-calendar.svg' },
            { id: '003', name: 'reminders', iconName: 'icon-reminders.svg' },
            { id: '004', name: 'planning', iconName: 'icon-planning.svg' },
          ],
        },
        {
          id: 1,
          title: 'company',
          sidePos: 'left',
          linkList: [
            { id: '021', name: 'history', iconName: '' },
            { id: '022', name: 'our team', iconName: '' },
            { id: '023', name: 'blog', iconName: '' },
          ],
        },
      ],
    };
  },
  methods: {
    openBurgerMenu() {
      this.isOpenBurger = true;
    },
    closeBurgerMenu() {
      this.isOpenBurger = false;
    },
  },
};
</script>

<style lang="scss" scoped>
.navbar {
  display: flex;
  align-items: center;
  width: 100%;
}
.navbar__background-burger {
  display: none;
  z-index: -10;
}
.navbar__logo {
  width: 87px;
  height: 27px;
  margin-right: 40px;
  user-select: none;
}
.navbar__burger-menu {
  display: none;
}
.navbar__wrapper {
  display: flex;
  width: 100%;
  justify-content: space-between;
}
.navbar__burger-close {
  display: none;
}
.navbar__link-container {
  display: flex;
  align-items: center;
}
.navbar__link {
  margin-left: 40px;
}
.navbar__button-container {
  display: flex;
}
.navbar__button {
  margin-left: 20px;
}

@media (max-width: 900px) {
  .navbar {
    position: relative;
    justify-content: space-between;
  }
  .navbar__background-burger {
    position: fixed;
    top: 0;
    left: 0;
    display: block;
    z-index: 4;
    width: 300%;
    height: 300%;
    background: var(--color-black);
    opacity: 0.7;
  }
  .navbar__burger-menu {
    display: block;
    width: 26px;
    cursor: pointer;
  }
  .navbar__wrapper {
    position: fixed;
    top: 0;
    right: -300px;
    flex-direction: column;
    justify-content: flex-start;
    width: 300px;
    height: 100%;
    padding: 30px;
    background: var(--color-white);
    z-index: 10;
    transition: all ease-out 0.2s;
  }
  .navbar__wrapper--open {
    right: 0px;
  }
  .navbar__burger-close {
    display: block;
    align-self: flex-end;
    width: 24px;
    height: 24px;
    margin-bottom: 20px;
    cursor: pointer;
  }
  .navbar__link-container {
    flex-direction: column;
  }
  .navbar__link {
    align-self: flex-start;
    margin-left: 0px;
    margin-top: 20px;
  }
  .navbar__button-container {
    display: flex;
    flex-direction: column;
    margin-top: 40px;
  }
  .navbar__button {
    margin-left: 0px;
    margin-bottom: 10px;
  }
}
</style>
