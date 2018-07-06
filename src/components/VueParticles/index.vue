<template>
<div>
   <canvas class="particles-background" ref="vue_particles_canvas">
   </canvas>
</div>

</template>
<script>

import Particles from 'particlesjs'
export default {
  name: 'vueCanvasNest',
  props: {
    config: {
      type: Object,
      default () {
        return {
          maxParticles: 100,
          sizeVariations: 3,
          speed: 0.5,
          color: '#000000',
          minDistance: 120,
          connectParticles: false,
          responsive: []
        }
      }
    }
  },
  data () {
    return {
      cn: ''
    }
  },
  mounted () {
    Particles.init({selector: '.particles-background', ...this.config})
  },
  beforeDestroy () {
    Particles.destroy()
  }
}
</script>
<style scoped>
.particles-background {
  position: absolute;
  display: block;
  top: 0;
  left: 0;
  z-index: -2;
}
</style>
