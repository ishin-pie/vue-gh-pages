<template>
  <timeline :items="items" />
</template>

<script>
import Timeline from './Timeline.vue'

export default {
  name: 'WorkExperience',
  components: {
    Timeline
  },
  data: () => ({
    items: [
      {
        year: '2022 - present',
        title: 'Application Integration Engineer',
        location: '@J Trust Royal Bank',
        description: `
            Focus on Javascript, Typescript and Spring Boot.<br />
        `
      },
      {
        year: '2021 - 2022',
        title: 'Senior Software Developer',
        location: '@Soramitsu Khmer Co., Ltd',
        description: `
            Develop web service (REST api) using Kotlin with Spring Boot.<br />
            Develop web applications using Vuejs.<br />
            Supporting Junior developers.
        `
      },
      {
        year: '2020 - 2021',
        title: 'Back-End Developer Lead',
        location: '@Pi Pay PLC',
        description: `
          Develop and maintain in-house back-end system of Pi Pay project.<br />
          Collaborate with mobile developers for feature improvement.
        `
      },
      {
        year: '2016 - 2017',
        title: 'Associate Software Engineer',
        location: '@DMI',
        description: `
          Develop web service (REST api) using Java with Spring Framework.<br />
          Develop web applications (front-end).
        `
      }
    ]
  })
}
</script>

<style>

</style>
