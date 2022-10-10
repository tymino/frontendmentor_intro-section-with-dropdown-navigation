<template>
  <div class="navbar">
    <my-icon class="navbar__logo" iconName="logo.svg" />
    <div class="navbar__wrapper">
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
  name: 'nav-bar',
  data() {
    return {
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
};
</script>

<style scoped>
.navbar {
  display: flex;
  align-items: center;
  width: 100%;
}
.navbar__logo {
  width: 87px;
  height: 27px;
  margin-right: 40px;
  user-select: none;
}
.navbar__wrapper {
  display: flex;
  width: 100%;
  justify-content: space-between;
}
.navbar__link-container {
  display: flex;
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
</style>
