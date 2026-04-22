<template>
  <div class="bg-slate-50 min-h-screen pt-28 pb-24">
    <div class="max-w-7xl mx-auto px-6 lg:px-10">
      <Breadcrumbs class="mb-8" />

      <!-- Header -->
      <div class="mb-16">
        <h1 class="text-5xl font-black text-slate-900 mb-4">Nos Projets</h1>
        <p class="text-slate-500 text-lg max-w-xl">
          Quelques exemples de réalisations — applications métier, solutions de gestion
          et déploiements développés par SYCOBE.
        </p>
      </div>

      <!-- Projects grid -->
      <div class="grid sm:grid-cols-2 lg:grid-cols-2 gap-6 mb-20">
        <div
          v-for="project in projects"
          :key="project.name"
          class="group flex flex-col bg-white border border-slate-100 shadow-sm rounded-2xl overflow-hidden hover:border-sky-200 transition-all duration-300 hover:-translate-y-1"
        >
          <!-- Image container -->
          <div class="w-full aspect-video bg-slate-800 overflow-hidden flex items-center justify-center">
            <img
              :src="project.icon"
              :alt="project.name"
              class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105"
            />
          </div>

          <!-- Card body -->
          <div class="p-6 flex flex-col flex-grow">
            <h2 class="text-slate-900 font-bold text-xl mb-2">{{ project.name }}</h2>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Breadcrumbs from '@/components/Breadcrumbs.vue';

export default {
  name: 'ProjectsPage',
  components: {
    Breadcrumbs
  },
  data() {
    return {
      projects: [
        {
          icon: '/projects/SaharaPeche.png',
          name: 'Sahara Pêche',
        },
        {
          icon: '/projects/saharaPaie.png',
          name: 'SAHARA PAIE',
        },
        {
          icon: '/projects/Saharamedic.png',
          name: 'SAHARAMEDIC',
        },
        {
          icon: '/projects/SaharaScolar.png',
          name: 'SAHARA SCOLAR',
        },
      ],
    }
  },
}
</script>