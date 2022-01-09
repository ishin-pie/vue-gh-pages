<template>
  <v-app :style="{ background: $vuetify.theme.themes.dark.background }">
    <v-main>
      <v-container class="wrapper px-16" style="max-width: 980px">
        <router-view />
      </v-container>
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
.wrapper {
  background-color: #1e1e1e;
}
</style>
