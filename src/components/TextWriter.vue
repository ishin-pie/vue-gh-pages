<template>
  <component :is="tag">
    <slot name="before"></slot>
    <span class="typed-text" :style="{color: textColor}">{{ typeValue }}</span>
    <span class="cursor" :style="{backgroundColor: cursorColor}" :class="{'typing': typeStatus}">&nbsp;</span>
    <slot name="after"></slot>
  </component>
</template>

<script>
import { setTimeout } from 'timers'

export default {
  name: 'TextWriter',
  props: {
    typeArray: {
      type: Array,
      required: true
    },
    typingSpeed: {
      type: Number,
      default: () => 200
    },
    erasingSpeed: {
      type: Number,
      default: () => 100
    },
    newTextDelay: {
      type: Number,
      default: () => 1000
    },
    tag: {
      type: String,
      default: () => 'div'
    },
    textColor: {
      type: String,
      default: () => ''
    },
    cursorColor: {
      type: String,
      default: () => '#fff'
    }
  },
  data: () => {
    return {
      typeValue: '',
      typeStatus: false,
      typeArrayIndex: 0,
      charIndex: 0
    }
  },
  methods: {
    typeText () {
      if (this.charIndex < this.typeArray[this.typeArrayIndex].length) {
        if (!this.typeStatus) { this.typeStatus = true }
        this.typeValue += this.typeArray[this.typeArrayIndex].charAt(this.charIndex)
        this.charIndex += 1
        setTimeout(this.typeText, this.typingSpeed)
      } else {
        this.typeStatus = false
        setTimeout(this.eraseText, this.newTextDelay)
      }
    },
    eraseText () {
      if (this.charIndex > 0) {
        if (!this.typeStatus) { this.typeStatus = true }
        this.typeValue = this.typeArray[this.typeArrayIndex].substring(0, this.charIndex - 1)
        this.charIndex -= 1
        setTimeout(this.eraseText, this.erasingSpeed)
      } else {
        this.typeStatus = false
        this.typeArrayIndex += 1
        if (this.typeArrayIndex >= this.typeArray.length) { this.typeArrayIndex = 0 }
        setTimeout(this.typeText, this.typingSpeed + 1000)
      }
    }
  },
  created () {
    setTimeout(this.typeText, this.newTextDelay + 200)
  }
}
</script>

<style lang="scss" scoped>
  // .container {
  //   width: 100%;
  //   height: 100vh;
  //   display: flex;
  //   justify-content: center;
  //   align-items: center;
  // }

  // span.typed-text {
  //   color: #D2B94B;
  // }

  span.cursor {
    display: inline-block;
    margin-left: 3px;
    width: 3px;
    // background-color: #fff;
    animation: cursorBlink 1s infinite;
  }

  span.cursor.typing {
    animation: none;
  }

  @keyframes cursorBlink {
    49% { background-color: #fff; }
    50% { background-color: transparent; }
    99% { background-color: transparent; }
  }
</style>
