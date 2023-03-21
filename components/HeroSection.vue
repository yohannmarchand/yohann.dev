<template>
  <div class="bg-gradient-to-r from-zinc-900 to-zinc-800 text-zinc-900 h-screen md:h-auto md:aspect-w-16 md:aspect-h-9 w-full">
    <img
      class="hidden inset-0 object-contains md:flex"
      src="~/assets/images/background.png"
    >

    <div class="inset-0 h-full flex flex-col space-y-8 items-center justify-center md:flex-row md:space-y-0 md:space-x-6">
      <div class="aspect-square">
        <img class="rounded-full" src="~/assets/images/avatar.jpg">
      </div>
      <div>
        <h1
          class="font-semibold text-4xl"
        >
          Yohann Marchand
        </h1>
        <h2
          class="text-3xl mt-4"
        >
          Web developer
        </h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeroSection"
}
</script>
