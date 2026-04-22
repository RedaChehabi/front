<template>
  <div class="bg-white min-h-screen pt-28 pb-24 flex items-center">
    <div class="max-w-4xl mx-auto px-6 lg:px-10 w-full">
      <div class="rounded-2xl bg-white border border-slate-100 shadow-sm p-10 text-center">
        <div class="w-20 h-20 rounded-full bg-sky-400 border border-sky-700 flex items-center justify-center text-4xl mx-auto mb-6">
          404
        </div>
        <h1 class="text-4xl font-black text-slate-900 mb-3">Page introuvable</h1>
        <p class="text-slate-500 mb-10 max-w-xl mx-auto">
          La page que vous cherchez n’existe pas (ou a été déplacée).
          Utilisez les liens ci-dessous pour continuer.
        </p>

        <div class="flex flex-col sm:flex-row gap-3 justify-center">
          <RouterLink
            to="/"
            class="px-7 py-3.5 rounded-lg bg-sky-500 text-white font-bold hover:bg-sky-700 transition-colors"
          >
            Retour à l’accueil
          </RouterLink>
          <RouterLink
            to="/services"
            class="px-7 py-3.5 rounded-lg border border-slate-100 shadow-sm text-slate-600 font-semibold hover:border-sky-300 hover:text-sky-600 transition-colors"
          >
            Nos services
          </RouterLink>
          <RouterLink
            to="/contact"
            class="px-7 py-3.5 rounded-lg border border-slate-100 shadow-sm text-slate-600 font-semibold hover:border-sky-300 hover:text-sky-600 transition-colors"
          >
            Contact
          </RouterLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NotFoundPage',
}
</script>

<style scoped></style>