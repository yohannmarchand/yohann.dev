<template>
  <div class="pb-64 relative min-h-screen bg-zinc-200 sm:items-center">
    <HeroSection />

    <LinePath class="py-8" :count="8" position="right" />

    <section class="px-4 pt-10 max-w-screen-xl md:px-10 mx-auto">
      <TechnoGrid />
    </section>

    <LinePath class="mt-8" :count="8" />

    <section class="px-4 pt-10 max-w-screen-xl md:px-10 mx-auto">
      <HistoryLine :startYear="2018"/>
    </section>
  </div>
</template>

<script>
import Line from "../components/global/LinePath.vue";
import NuxtLogo from "../components/NuxtLogo.vue";
import PathComponent from "../components/global/PathComponent.vue";
import LinePath from "../components/global/LinePath.vue";

export default {
  name: 'IndexPage',
  components: {LinePath, PathComponent, NuxtLogo, Line },
}
</script>
