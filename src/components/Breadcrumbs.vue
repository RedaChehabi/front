<template>
  <nav aria-label="Breadcrumb" class="flex items-center gap-2 text-sm">
    <RouterLink to="/" class="text-slate-900 hover:text-sky-600 transition-colors">
      Accueil
    </RouterLink>

    <span v-for="(crumb, idx) in crumbs" :key="crumb.to" class="inline-flex items-center gap-2">
      <span class="text-slate-600">/</span>
      <RouterLink
        v-if="idx < crumbs.length - 1"
        :to="crumb.to"
        class="text-slate-700 hover:text-sky-600 transition-colors"
      >
        {{ crumb.label }}
      </RouterLink>
      <span v-else class="text-slate-500 font-semibold">
        {{ crumb.label }}
      </span>
    </span>
  </nav>
</template>

<script setup>
import { computed } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()

const LABELS = {
  about: 'Présentation',
  projects: 'Réalisation',
  services: 'Services',
  contact: 'Contact',
  products: 'Produits',
  mikrotik: 'MikroTik',
}

function formatSegment(seg) {
  if (!seg) return ''
  const cleaned = String(seg).replace(/\/+$/, '').toLowerCase()
  if (LABELS[cleaned]) return LABELS[cleaned]
  const withSpaces = cleaned.replace(/-/g, ' ')
  return withSpaces.charAt(0).toUpperCase() + withSpaces.slice(1)
}

const crumbs = computed(() => {
  const segments = route.path.split('/').filter(Boolean)
  const result = []
  let acc = ''
  for (const seg of segments) {
    acc += `/${seg}`
    result.push({ to: acc, label: formatSegment(seg) })
  }
  return result
})
</script>

<style scoped></style>
