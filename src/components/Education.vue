<template>
  <timeline :items="items" />
</template>

<script>
import Timeline from './Timeline.vue'

export default {
  name: 'Education',
  components: {
    Timeline
  },
  data: () => ({
    items: [
      {
        year: '2017 - 2020',
        title: 'Master\'s Degree in Computer Software and Theory',
        location: 'Beihang University, Beijing',
        description: ''
      },
      {
        year: '2012 - 2016',
        title: 'Bachelor\'s Degree in Computer Science and Engineering',
        location: 'Royal University of Phnom Penh',
        description: ''
      },
      {
        year: '2012 - 2017',
        title: 'Bachelor\'s Degree in Teaching English as a Foreign Language',
        location: 'Beltei International University',
        description: ''
      },
      {
        year: '2015 - 2016',
        title: 'Software Development Training Program',
        location: 'Korea Software HRD Center',
        description: ''
      }
    ]
  })
}
</script>
