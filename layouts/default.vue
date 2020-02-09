<template>
  <div>
    <nuxt :style="dynamicHue" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      clientX: 0,
      clientY: 0,
      windowWidth: 0,
      windowHeight: 0,
      hoverActive: true
    }
  },
  computed: {
    colorHue() {
      const hue = (360 / this.windowWidth) * this.clientX
      return parseInt(hue, 10)
    },
    dynamicHue() {
      return {
        filter: `hue-rotate(${this.colorHue + 'deg'})`
      }
    }
  },
  mounted() {
    window.addEventListener('resize', this.handleResize)
    document
      .getElementsByTagName('body')[0]
      .addEventListener('mousemove', this.updateMouseLocation)
    this.handleResize()
  },
  destroy() {
    window.removeEventListener('resize', this.handleResize)
  },
  methods: {
    updateMouseLocation(e) {
      const { clientX, clientY } = e
      if (this.hoverActive) {
        this.clientX = clientX
        this.clientY = clientY
      }
    },
    handleResize() {
      this.windowWidth = window.innerWidth
      this.windowHeight = window.innerHeight
    }
  }
}
</script>

<style lang="scss">
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}
</style>
