<template>
  <div :style="`max-height: ${maxHeight}px; height: ${maxHeight}px`">
    <div
      ref="line"
      class="w-4 bg-blue-600 rounded-full transition-all"
      :style="`height: ${height}px`"
    />
  </div>
</template>

<script>

export default {
  data() {
    return {
      height: 0
    }
  },

  props: {
    maxHeight: Number,
  },

  mounted() {
    const el = this.$refs.line

    const bottomObserver = new IntersectionObserver((entries, observer) => {
      entries.forEach(entry => {
        if ((window.innerHeight + window.pageYOffset) >= document.body.offsetHeight) {
          this.height = 0
        }

        if (entry.isIntersecting && !((window.innerHeight + window.pageYOffset) >= document.body.offsetHeight)) {
          if (this.height > 0) {
            this.height -= this.maxHeight / 10
          }
        }
      });
    }, {
      rootMargin: '-100% 0px 0px 0px',
      threshold: 0
    })

    const topObserver = new IntersectionObserver((entries, observer) => {
      entries.forEach(entry => {
        if (!entry.isIntersecting) {
          if ((window.innerHeight + window.pageYOffset) >= document.body.offsetHeight) {
            this.height = this.maxHeight

            return
          }

          if (this.height < this.maxHeight && window.pageYOffset !==0) {
            this.height += this.maxHeight / 5
          }
        }
       });
    }, {
        rootMargin: '0px 0px 0px 0px',
        threshold: 0
    })

    document.addEventListener('scroll', (event) => {
      if ((window.innerHeight + window.pageYOffset) >= document.body.offsetHeight) {
        this.height = this.maxHeight
      } else if(window.pageYOffset === 0) {
        this.height = 0
      }
    })

    bottomObserver.observe(el)
    topObserver.observe(el)
  }
}
</script>
