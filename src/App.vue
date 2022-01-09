<template>
  <v-app :style="{ background: $vuetify.theme.themes.dark.background }">
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

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
</style>
