<template>
  <v-timeline
    :reverse="!$vuetify.breakpoint.xs"
    :dense="$vuetify.breakpoint.xs"
  >
    <v-timeline-item
      v-for="(item, i) in items"
      :key="i"
      color="white"
      small
    >
      <template v-slot:opposite>
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
  }
}
</script>
