<template>
  <div class="space-y-4">
    <div>
      <div
        v-for="i in count"
        :key="i"
        ref="dot"
        class="h-3 w-3 bg-zinc-200 rounded-full transition-opacity"
        style="opacity: 0"
        :style="{
          marginLeft: getPosition(i),
        }"
      />
    </div>
    <div/>
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
    }
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

    dots.map(dot => observer.observe(dot))
  },

  methods: {
    getPosition(index) {
      const radius = this.count * 2

      const angle = (Math.PI / radius) * index

      const x = index * radius * Math.cos(angle)

      if (this.position === 'left') {
        return x + 'px'
      } else {
        return - x + 'px'
      }

    }
  }
}
</script>
