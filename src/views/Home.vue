<template>
  <div class="home">
    <profile class="mt-12" />
    <v-divider class="my-8" />
    <!-- <text-writer
      :typeArray="['fun!', 'awesome!', 'life!']"
      textColor="#C62828"
      class="pb-4"
    >
      <template #before>
        <span>Coding is </span>
      </template>
    </text-writer> -->
    <p class="about-me">
      A talented software developer, with a strong educational background in computer programming, who has {{ getExpYears }}+ years' background in software development, both Backend and Frontend.
    </p>
    <div class="heading">Work Experiences</div>
    <work-experience />
    <div class="heading">Education</div>
    <education />
    <div class="heading">Skills</div>
    <skills />
    <p class="copyright">Copyright&copy;2022 - Ishin Vin</p>
  </div>
</template>

<script>
import Profile from '../components/Profile.vue'
// import TextWriter from '../components/TextWriter.vue'
import WorkExperience from '../components/WorkExperience.vue'
import Education from '../components/Education.vue'
import Skills from '../components/Skills.vue'

export default {
  name: 'Home',
  metaInfo: {
    title: 'Home'
  },
  components: {
    Profile,
    // TextWriter,
    WorkExperience,
    Education,
    Skills
  },
  data () {
    return {
      current: new Date()
    }
  },
  computed: {
    getExpYears () {
      return this.current.getFullYear() - 2017
    }
  }
}
</script>

<style lang="scss" scoped>
.heading {
  font-size: 16px;
  padding-top: 48px;
  color: #FC929E;
  // color: #66D9EF;
  // color: #A6E22E;
}
.about-me {
  margin: 0 auto;
  width: 90%;
}
.copyright {
  font-size: 12px;
  margin-top: 120px;
  margin-bottom: 32px;
}
</style>
