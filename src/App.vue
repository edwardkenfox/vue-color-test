<template>
  <div id="app">
    <button @click="toggleColorPicker">Show color picker</button>
    <color-picker v-model="colors" v-show="colorPickerShown"></color-picker>
  </div>
</template>

<script>
import { Chrome as ColorPicker } from 'vue-color'

var defaultProps = {
  hex: '#194d33',
  hsl: {h: 150, s: 0.5, l: 0.2, a: 1 },
  hsv: {h: 150, s: 0.66, v: 0.30, a: 1 },
  rgba: {r: 25, g: 77, b: 51, a: 1 },
  a: 1
}

export default {
  name: 'app',
  components: {
    'color-picker': ColorPicker
  },
  data: function() {
    return {
      colors: defaultProps,
      colorPickerShown: false
    }
  },
  methods: {
    toggleColorPicker() {
      const current = this.colorPickerShown
      this.colorPickerShown = !current
    }
  }
}
</script>
