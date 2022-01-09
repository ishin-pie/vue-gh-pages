<template>
  <v-timeline reverse>
    <v-timeline-item
      v-for="(item, i) in items"
      :key="i"
      :color="randomColors[i]"
      small
    >
      <template v-slot:opposite>
        <span
          :class="`font-weight-bold ${randomColors[i]}--text`"
          v-text="item.year"
        ></span>
      </template>
      <div class="py-4">
        <h3 :class="`font-weight-light ${randomColors[i]}--text`">
          {{item.title}}
        </h3>
        <h4 class="font-weight-bold mb-4">
          {{item.location}}
        </h4>
        <div v-html="item.description" class="blue-grey--text text--lighten-2"></div>
        <!-- {{ randomColors }} -->
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
      interval: null,
      colors: ['cyan', 'green', 'pink', 'orange', 'lime', 'light-blue', 'teal', 'amber', 'red', 'blue-grey', 'brown', 'grey', 'indigo'],
      randomColors: []
    }
  },
  mounted () {
    this.getColors()
  },
  methods: {
    getColors () {
      this.interval = setInterval(() => {
        const temp = [];
        [...Array(this.items.length)].forEach((_, i) => {
          temp.push(this.colors[Math.floor(Math.random() * this.colors.length)])
        })
        this.randomColors = temp
      }, 1000)
    }
  },
  beforeDestroy () {
    clearInterval(this.interval)
  }
}
</script>
