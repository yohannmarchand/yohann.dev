<template>
  <div class="relative min-h-screen bg-zinc-200 sm:items-center">

    <HeroSection />

    <div class="h-16 bg-zinc-800">
    </div>

    <div class="bg-zinc-900 text-white px-6 py-8">
      <h5 class="text-lg">Mon Parcours</h5>

      <div>
        <LinePath class="flex flex-col items-center" :count="20" />

        <LinePath class="flex flex-col items-center" :count="20" position="right" />
        <LinePath class="flex flex-col items-center" :count="20" />
        <LinePath class="flex flex-col items-center" :count="20" position="right" />
      </div>

    </div>
  </div>
</template>

<script>
import Line from "../components/global/LinePath.vue";
import NuxtLogo from "../components/NuxtLogo.vue";

export default {
  name: 'IndexPage',
  components: {NuxtLogo, Line },
}
</script>
