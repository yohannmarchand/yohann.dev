<template>
  <div class="mx-auto w-fit px-4 pt-10 max-w-screen-xl text-blue-600 font-bold md:px-10 text-center text-3xl flex flex-col">
    <div>{{ title }}</div>
    <div class="mt-1 flex justify-center space-x-3">
      <div class="h-1.5 w-4 bg-blue-500 rounded-full" />
      <div class="h-1.5 grow bg-blue-500 rounded-full" />
      <div class="h-1.5 w-4 bg-blue-500 rounded-full" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
  }
}
</script>
