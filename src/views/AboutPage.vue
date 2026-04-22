<template>
  <div class="bg-slate-50 min-h-screen pt-28 pb-24">
    <div class="max-w-7xl mx-auto px-6 lg:px-10">
      <Breadcrumbs class="mb-8" />

      <div class="mb-16">
        <p class="text-sky-600 text-xs font-bold tracking-widest uppercase mb-4">À Propos de Nous</p>
        <h1 class="text-5xl lg:text-6xl font-black text-slate-900 leading-tight mb-6">
          Expertise IT & Télécoms<br/>au cœur de la Mauritanie
        </h1>
        <p class="text-slate-500 text-lg leading-relaxed max-w-2xl">
          SYCOBE accompagne entreprises et institutions dans leur transformation
          numérique depuis plus de 20 ans — avec rigueur, compétence et ancrage local.
        </p>
        <div class="mt-6 h-px bg-slate-800 max-w-2xl"></div>
      </div>

      <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 mb-16">
        <div
          v-for="stat in stats"
          :key="stat.label"
          class="rounded-2xl bg-white border border-slate-100 shadow-sm p-6"
        >
          <p class="text-slate-900 font-black text-4xl mb-2">{{ stat.value }}</p>
          <p class="text-slate-600 text-sm leading-relaxed">{{ stat.label }}</p>
        </div>
      </div>

      <div class="mb-16">
        <p class="text-slate-600 text-lg leading-relaxed">
          Fondée le 27 novembre 2000 à Nouadhibou sous le nom SYCOBE, la société a bâti au fil des années
          une solide réputation dans les domaines de l'informatique, des télécommunications, de la
          maintenance et des services internet. Aujourd'hui basée à Nouakchott avec une représentation active
          à Nouadhibou, SYCOBE opère à l'échelle nationale et s'appuie sur des partenariats internationaux
          pour partager expertises et compétences. L'entreprise est dirigée par un expert IT agréé disposant de
          plus de 15 ans d'expérience, entouré d'une équipe solide et pluridisciplinaire.
        </p>
      </div>

      <div class="grid sm:grid-cols-2 gap-4 mb-16">
        <div
          v-for="domain in domains"
          :key="domain.title"
          class="rounded-2xl bg-white border border-slate-100 hover:border-sky-200 transition-all duration-300 hover:-translate-y-1 p-6"
        >
          <div class="w-10 h-10 rounded-xl flex items-center justify-center mb-4" :class="domain.bg">
            <component :is="domain.icon" class="w-5 h-5" :class="domain.color" />
          </div>
          <h3 class="text-slate-900 font-bold text-base mb-2">{{ domain.title }}</h3>
          <p class="text-slate-600 text-sm leading-relaxed">{{ domain.desc }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Breadcrumbs from '@/components/Breadcrumbs.vue';
import {
  Monitor,
  Wifi,
  ShieldCheck,
  Users,
} from 'lucide-vue-next'

export default {
  name: 'AboutPage',
  components: {
    Monitor,
    Wifi,
    ShieldCheck,
    Users,
    Breadcrumbs
  },
  data() {
    return {
      stats: [
        { value: '+20',  label: "ans d'expérience dans l'IT & Télécoms" },
        { value: '+15',  label: "ans d'expertise du dirigeant certifié" },
        { value: '2001', label: 'année de fondation officielle (SYCOBE)' },
      ],
      domains: [
        {
          icon: 'Monitor',
          bg: 'bg-blue-500/10',
          color: 'text-blue-400',
          title: 'Développement & Systèmes',
          desc: "Solutions logicielles sur mesure, bases de données, systèmes d'exploitation et intégration.",
        },
        {
          icon: 'Wifi',
          bg: 'bg-cyan-500/10',
          color: 'text-cyan-400',
          title: 'Réseaux & Infrastructures',
          desc: "Mise en service et supervision d'infrastructures réseau, wifi, LAN/WAN et télécom.",
        },
        {
          icon: 'ShieldCheck',
          bg: 'bg-emerald-500/10',
          color: 'text-emerald-400',
          title: 'Audit & Sécurité IT',
          desc: "Audit de sécurité informatique, contrôle et conformité des systèmes d'information.",
        },
        {
          icon: 'Users',
          bg: 'bg-purple-500/10',
          color: 'text-purple-400',
          title: 'Formation & Conseil',
          desc: "Formations IT, transfert de compétences et accompagnement des équipes techniques.",
        },
      ]
    }
  },
}
</script>