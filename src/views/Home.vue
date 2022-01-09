<template>
  <div class="home">
    <profile class="mt-12" />
    <v-divider class="my-8" />
    <text-writer
      :typeArray="['fun!', 'awesome!', 'life!']"
      textColor="#C62828"
      class="pb-4"
    >
      <template #before>
        <span>Coding is </span>
      </template>
    </text-writer>
    <p class="about-me">
      A talented software developer, with a strong educational background in computer programming, who has {{ getExpYears }}+ years' background in software development, both Backend and Frontend.
      <br /><br />
      A curious learner and team player searching for opportunity to utilize my technical competencies and working knowledge of software development to grow as a qualified Software Engineer.
    </p>
    <div class="heading">Skills</div>
    <skills />
    <div class="heading mt-4">Work Experiences</div>
    <work-experience />
    <div class="heading mt-4">Education</div>
    <education />
    <div class="copyright">Copyright &copy;2022 - Ishin Vin</div>
  </div>
</template>

<script>
import Profile from '../components/Profile.vue'
import TextWriter from '../components/TextWriter.vue'
import WorkExperience from '../components/WorkExperience.vue'
import Education from '../components/Education.vue'
import Skills from '../components/Skills.vue'

export default {
  name: 'Home',
  components: {
    Profile,
    TextWriter,
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
      return this.current.getFullYear() - 2019
    }
  }
}
</script>

<style lang="scss" scoped>
.heading {
  font-size: 22px;
  padding-top: 48px;
  color: #FFAB00;
}
.about-me {
  margin: 0 auto;
  width: 70%;
}
.copyright {
  margin-top: 120px;
  margin-bottom: 32px;
}
</style>
