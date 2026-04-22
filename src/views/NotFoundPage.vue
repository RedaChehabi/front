<template>
  <div class="bg-slate-50 min-h-screen flex items-center justify-center px-6">
    <div class="text-center max-w-lg w-full">

      <p class="text-[10rem] font-black text-slate-100 leading-none select-none">404</p>

      <div class="w-16 h-16 rounded-2xl bg-sky-50 border border-sky-100 flex items-center justify-center text-3xl mx-auto -mt-8 mb-6 shadow-sm">
        🔍
      </div>

      <h1 class="text-3xl font-black text-slate-900 mb-3">Page introuvable</h1>
      <p class="text-slate-500 mb-8 leading-relaxed">
        La page que vous cherchez n'existe pas ou a été déplacée.
        Utilisez les liens ci-dessous pour continuer.
      </p>

      <div class="flex flex-col sm:flex-row gap-3 justify-center">
        <RouterLink
          to="/"
          class="px-7 py-3.5 rounded-xl bg-sky-700 text-white font-bold hover:bg-sky-600 transition-colors"
        >
          ← Retour à l'accueil
        </RouterLink>
        <RouterLink
          to="/services"
          class="px-7 py-3.5 rounded-xl border border-slate-200 text-slate-600 font-semibold hover:border-sky-300 hover:text-sky-700 transition-colors"
        >
          Nos services
        </RouterLink>
        <RouterLink
          to="/contact"
          class="px-7 py-3.5 rounded-xl border border-slate-200 text-slate-600 font-semibold hover:border-sky-300 hover:text-sky-700 transition-colors"
        >
          Contact
        </RouterLink>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: 'NotFoundPage',
}
</script>