<template>
  <!-- <v-app :style="{ background: $vuetify.theme.themes.dark.background }"> -->
  <v-app>
    <v-main>
      <v-container class="wrapper px-sm-16" style="max-width: 1080px">
        <router-view />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  metaInfo: {
    title: 'Home',
    titleTemplate: '%s | Ishin Vin'
  }
}
</script>

<style lang="scss">
@font-face {
  font-family: "Monaco";
  src: local("Monaco"),
   url(./assets/font/Monaco.ttf) format("truetype");
}

#app {
  font-family: Monaco, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;
}
p, span {
  font-size: 14px;
}
// .wrapper {
//   background-color: #1e1e1e;
// }
</style>
