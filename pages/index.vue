<template>
  <div class="relative min-h-screen bg-zinc-200 sm:items-center">
    <HeroSection />

    <div class="bg-zinc-900 text-white px-6 py-8">
      <div class="space-y-10 px-4 md:px-20">
        <LinePath :count="10" :parcour="parcours[0]" />
        <LinePath :count="10" position="right" :parcour="parcours[1]" />
        <LinePath :count="10" :parcour="parcours[2]" />
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

  data() {
    return {
      parcours: [
        { title: 'DUT MMI', school:'IUT Angouleme', years: '2018-2020' },
        { title: 'LP DAWIN', school: 'IUT Bordeaux', years: '2020-2021' },
        { title: 'Master Informatique', school: 'Ynov Campus', years: '2021-2023' }
      ]
    }
  }
}
</script>
