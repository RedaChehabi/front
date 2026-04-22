<template>
  <div class="bg-slate-50 min-h-screen pt-24 pb-16">
    <div class="max-w-7xl mx-auto px-6 lg:px-10">
      <Breadcrumbs class="mb-8" />
      <!-- Header -->
      <div class="text-center mb-10">
        <h1 class="text-5xl font-black text-slate-900 mb-3">Parlons de votre projet</h1>
        <p class="text-slate-500 max-w-2xl mx-auto">
          Besoin d'un devis, d'un audit, d'un déploiement ou d'une formation ?
          Envoyez-nous un message et nous vous répondrons rapidement.
        </p>
      </div>

      <Contactsection />
    </div>
  </div>
</template>

<script>
import Breadcrumbs from '@/components/Breadcrumbs.vue';
import Contactsection from '@/components/Contactsection.vue'


export default {
  name: 'ContactPage',
  components: { 
    Contactsection,
    Breadcrumbs
  },
}
</script>