<template>
  <div class="main">
    <my-dropdown v-for="data in dropdownData" :key="data.id" :data="data" />
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {},
  data() {
    return {
      svg: 'client-audiophile',
      dropdownData: [
        {
          id: 0,
          title: 'features',
          sidePos: 'right',
          linkList: [
            { id: '001', name: 'todo list', svgName: 'icon-todo.svg' },
            { id: '002', name: 'calendar', svgName: 'icon-calendar.svg' },
            { id: '003', name: 'reminders', svgName: 'icon-reminders.svg' },
            { id: '004', name: 'planning', svgName: 'icon-planning.svg' },
          ],
        },
        {
          id: 1,
          title: 'company',
          sidePos: 'left',
          linkList: [
            { id: '021', name: 'history', svgName: '' },
            { id: '022', name: 'our team', svgName: '' },
            { id: '023', name: 'blog', svgName: '' },
          ],
        },
      ],
    };
  },
};
</script>

<style>
:root {
  --color-white: hsl(0, 0%, 98%);
  --color-gray: hsl(0, 0%, 41%);
  --color-black: hsl(0, 0%, 8%);
}
#app {
  font-family: 'Epilogue', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  padding: 20px;
}

.main {
  display: flex;
  justify-content: center;
}
</style>
