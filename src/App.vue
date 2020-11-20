<template>
  <v-app id="app">
    <router-view></router-view>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  components: {},

  data: () => ({
    //
  }),
};
</script>
<style lang="scss" scoped>
body {
  background: #f6f9fc;
}
#app {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
:root {
  font-size: 10px;
}
</style>
