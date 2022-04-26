<template>
  <v-timeline
    :reverse="!$vuetify.breakpoint.xs"
    :dense="$vuetify.breakpoint.xs"
  >
    <!-- :color="randomColors[i]" -->
    <v-timeline-item
      v-for="(item, i) in items"
      :key="i"
      color="white"
      small
    >
      <template v-slot:opposite>
        <!-- :class="`font-weight-bold ${randomColors[i]}--text`" -->
        <span v-text="item.year"></span>
      </template>
      <div :class="{'text-left': $vuetify.breakpoint.xs}">
        <p>
          {{item.title}}
        </p>
        <p style="color: #E6DB74">
          {{item.location}}
        </p>
        <p v-html="item.description" style="color: #B2B2B2"></p>
      </div>
    </v-timeline-item>
  </v-timeline>
</template>

<script>
export default {
  name: 'Timeline',
  props: {
    items: {
      type: Array,
      required: true
    }
  },
  data () {
    return {
      // interval: null
      // colors: ['cyan', 'green', 'pink', 'orange', 'lime', 'light-blue', 'teal', 'amber', 'red', 'blue-grey', 'brown', 'grey', 'indigo'],
      // randomColors: []
    }
  },
  mounted () {
    // this.getColors()
  },
  methods: {
    // getColors () {
    //   this.interval = setInterval(() => {
    //     const temp = [];
    //     [...Array(this.items.length)].forEach((_, i) => {
    //       temp.push(this.colors[Math.floor(Math.random() * this.colors.length)])
    //     })
    //     this.randomColors = temp
    //   }, 1000)
    // }
  }
  // beforeDestroy () {
  //   clearInterval(this.interval)
  // }
}
</script>
