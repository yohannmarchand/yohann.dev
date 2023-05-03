<template>
  <div class="pb-64 relative min-h-screen bg-zinc-200 sm:items-center">
    <HeroSection />

    <LinePath class="py-8" :count="8" position="right" />

    <SectionTitle title="Technologies"/>

    <section class="px-4 pt-10 max-w-screen-xl md:px-10 mx-auto">
      <TechnoGrid />
    </section>

    <LinePath class="mt-8" :count="8" />

    <SectionTitle title="Mon parcours"/>

    <section class="px-4 pt-10 max-w-screen-xl md:px-10 mx-auto">
      <HistoryLine :startYear="2018"/>
    </section>

    <LinePath class="mt-8" :count="8" position="right" />

    <SectionTitle title="Mes projets"/>
  </div>
</template>

<script>
import Line from "../components/global/LinePath.vue";
import NuxtLogo from "../components/NuxtLogo.vue";
import PathComponent from "../components/global/PathComponent.vue";
import LinePath from "../components/global/LinePath.vue";
import SectionTitle from "../components/global/SectionTitle.vue";

export default {
  name: 'IndexPage',
  components: {SectionTitle, LinePath, PathComponent, NuxtLogo, Line },
}
</script>
