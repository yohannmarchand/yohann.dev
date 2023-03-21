<template>
  <div class="py-6">
      <div class="text-lg">{{ parcour.title }}</div>
      <div class="text-md">{{ parcour.years }}</div>
      <div class="text-md">{{ parcour.school }}</div>
  </div>
</template>

<script>
export default {
  name: "ParcourCard",

  props: {
    parcour: Object
  }
}
</script>
