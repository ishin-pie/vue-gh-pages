<template>
  <div class="profile">
    <v-row>
      <v-col cols="12">
        <v-avatar size="150" :style="getComputedStyle" class="profile-avatar">
          <img
            src="https://avatars.githubusercontent.com/u/63244532?v=4"
            alt="Ishin Vin"
          >
        </v-avatar>
      </v-col>
      <v-col cols="12" class="pt-0">
        <div class="full-name white--text">Ishin Vin</div>
        <text-writer
          :typeArray="['Software Developer in Cambodia']"
          tag="h3"
          textColor="#FFAB00"
        >
          <template #after>
            <span style="font-size: 24px;">🇰🇭</span>
          </template>
        </text-writer>
      </v-col>
      <v-col>
        <div>
          <span><a href="https://github.com/ishin-pie" target="_blank"><img src="https://img.shields.io/badge/-GitHub-white?style=flat&logo=github&logoColor=black" alt="GitHub" /></a>&nbsp;</span>
          <span><a href="mailto:ishin.pie@gmail.com" target="_blank"><img src="https://img.shields.io/badge/-Gmail-white?style=flat&logo=gmail" alt="Gmail" /></a>&nbsp;</span>
          <span><a href="https://t.me/ishinvin" target="_blank"><img src="https://img.shields.io/badge/-Telegram-white?style=flat&logo=telegram" alt="Telegram" /></a></span>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import TextWriter from './TextWriter.vue'

export default {
  name: 'Profile',
  components: {
    TextWriter
  },
  data () {
    return {
      interval: null,
      colors: ['#D32F2F', '#E91E63', '#9C27B0', '#3F51B5', '#2196F3', '#00BCD4', '#009688', '#4CAF50', '#CDDC39', '#FFC107', '#607D8B', '#9E9E9E'],
      randomColors: null
    }
  },
  mounted () {
    this.getColors()
  },
  computed: {
    getComputedStyle () {
      return {
        borderColor: this.randomColors
      }
    }
  },
  methods: {
    getColors () {
      this.interval = setInterval(() => {
        this.randomColors = this.colors[Math.floor(Math.random() * this.colors.length)]
      }, 1000)
    }
  },
  beforeDestroy () {
    clearInterval(this.interval)
  }
}
</script>

<style lang="scss" scoped>
.profile-avatar {
  border-width: 5px;
  border-style: solid;
}
.full-name {
  font-size: 2rem;
}
</style>
