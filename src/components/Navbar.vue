<template>
  <div class="navbar">
    <my-icon class="navbar__logo" iconName="logo.svg" />
    <div class="navbar__wrapper">
      <div class="navbar__links">
        <my-dropdown v-for="data in dropdownData" :key="data.id" :data="data" />
        <my-link linkName="careers" />
        <my-link linkName="About" />
      </div>
      <div class="navbar__buttons"></div>
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
}
.navbar__wrapper {
  display: flex;
}
.navbar__links {
  display: flex;
}
.navbar__buttons {
  display: flex;
}
.navbar__logo {
  /* width: 100px;
  height: 100px; */
}
</style>
