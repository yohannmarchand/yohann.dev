<template>
  <div class="relative">
    <div class="space-y-10 flex flex-col items-center">
      <div
        v-for="i in count"
        :key="i"
        ref="dot"
        class="h-4 w-4 bg-blue-500 rounded-full transition-opacity"
        style="opacity: 0"
      />
    </div>

    <div
      ref="parcour"
      class="absolute inset-0 flex items-center transition-opacity"
      :class="position === 'left' ? 'justify-end' : 'justify-start'"
      style="opacity: 0"
    >
    </div>
  </div>
</template>

<script>

export default {
  props: {
    count: {
      type: Number,
      default: 10
    },

    position: {
      type: String,
      default: 'left',
    },

    parcour: Object,
  },

  mounted() {
    const dots = this.$refs.dot

    let observer = new IntersectionObserver((entries, observer) => {
      entries.forEach(entry => {
        window.setTimeout(() => {
          if (entry.isIntersecting)
            entry.target.style.opacity = 1
          else
            entry.target.style.opacity = 0
        }, 750)
      });
    }, {threshold: 1})

    observer.observe(this.$refs.parcour)

    dots.map((dot, index) => {
      observer.observe(dot)
      dot.style.marginRight= this.getPosition(index)
    })

    window.addEventListener('resize', () => {
      dots.map((dot, index) => dot.style.marginRight= this.getPosition(index))
    })
  },

  methods: {
    getPosition(index) {
      const radius = this.count * 2
      const angle = (Math.PI / radius) * index
      const x = radius * Math.cos(angle) * (window.screen.width / 100)

      if (this.position === 'left') {
        return x + 'px'
      } else {
        return - x + 'px'
      }

    }
  }
}
</script>
