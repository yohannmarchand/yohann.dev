<template>
  <div class="transition-all relative min-h-screen bg-zinc-200 sm:items-center">
    <HeroSection />

    <div class="p-10 max-w-screen-lg mx-auto">
      <HistoryLine :startYear="2018"/>
    </div>
  </div>
</template>

<script>
import Line from "../components/global/LinePath.vue";
import NuxtLogo from "../components/NuxtLogo.vue";
import PathComponent from "../components/global/PathComponent.vue";

export default {
  name: 'IndexPage',
  components: {PathComponent, NuxtLogo, Line },
}
</script>
