<template>
  <div
    class="border overflow-auto border-blue-600 bg-zinc-200 rounded p-4 transition-all hover:scale-110"
    :class="isOpen ? 'absolute top-4 left-0 w-full h-full z-50 border-2': 'cursor-pointer'"
  >
    <button
      v-if="isOpen"
      class="mb-4"
      @click.stop="onClose"
    >
      <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
        <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
      </svg>
    </button>

    <div
      @click.stop="onClick"
    >
      <div>{{ content.title }}</div>
      <div class="flex space-x-1 items-center">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4">
          <path stroke-linecap="round" stroke-linejoin="round" d="M15 10.5a3 3 0 11-6 0 3 3 0 016 0z" />
          <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1115 0z" />
        </svg>

        <div> {{ content.location }}</div>
      </div>
      <div
        v-if="isOpen"
        class="mt-4"
        v-html="content.description"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false
    }
  },

  props: {
    content: Object
  },

  methods: {
    onClick() {
      this.isOpen = true
      this.$emit('click', this.$el)
    },

    onClose() {
      this.isOpen = false
      this.$emit('close', this.$el)
    }
  }
}
</script>
