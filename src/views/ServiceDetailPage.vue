<template>
  <div class="bg-slate-50 min-h-screen pt-28 pb-24">
    <div class="max-w-7xl mx-auto px-6 lg:px-10">

      <div v-if="!service" class="rounded-2xl bg-white border border-slate-100 shadow-sm p-10 text-center">
        <h1 class="text-3xl font-black text-slate-900 mb-3">Service introuvable</h1>
        <p class="text-slate-500 mb-8">Le service demandé n'existe pas ou l'URL est incorrecte.</p>
        <RouterLink to="/services" class="px-7 py-3.5 rounded-lg bg-sky-700 text-white font-bold hover:bg-sky-600 transition-colors">
          Retour aux services
        </RouterLink>
      </div>

      <template v-else>

        <RouterLink
          to="/services"
          class="inline-flex items-center gap-2 text-slate-400 hover:text-sky-600 text-sm mb-10 transition-colors"
        >
          <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" d="M15 19l-7-7 7-7"/>
          </svg>
          Retour aux services
        </RouterLink>

        <div class="grid lg:grid-cols-2 gap-12 items-center mb-16">
          <div>
            <div
              class="inline-flex items-center gap-2 px-3 py-1.5 rounded-full text-xs font-semibold mb-5"
              :class="service.badgeBg + ' ' + service.badgeText"
            >
              {{ service.title }}
            </div>
            <h1 class="text-4xl lg:text-5xl font-black text-slate-900 leading-tight mb-5">
              {{ service.heading }}
            </h1>
            <p class="text-slate-500 text-lg leading-relaxed mb-8">
              {{ service.longDesc }}
            </p>
          </div>

          <div class="rounded-2xl overflow-hidden shadow-sm" :class="service.iconBg">
            <img
              v-if="service.image"
              :src="service.image"
              :alt="service.title"
              class="w-full h-72 object-cover rounded-2xl"
            />
          </div>
        </div>

        <div class="grid lg:grid-cols-3 gap-6 items-start">

          <div class="lg:col-span-2 flex flex-col gap-6">

            <div class="rounded-2xl bg-white border border-slate-100 shadow-sm p-8">
              <h2 class="text-xl font-black text-slate-900 mb-2">Ce que nous faisons</h2>
              <p class="text-slate-500 text-sm mb-6">
                Un accompagnement de bout en bout : cadrage, déploiement, tests et support.
              </p>
              <ul class="grid sm:grid-cols-2 gap-3">
                <li
                  v-for="item in service.bullets"
                  :key="item"
                  class="flex items-start gap-3 text-slate-600 text-sm"
                >
                  <span class="w-5 h-5 rounded-full flex items-center justify-center flex-shrink-0 mt-0.5" :class="service.checkBg">
                    <svg class="w-3 h-3" :class="service.checkColor" fill="none" stroke="currentColor" stroke-width="3" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/>
                    </svg>
                  </span>
                  {{ item }}
                </li>
              </ul>
            </div>
          </div>

          <div class="flex flex-col gap-5">
            <div class="rounded-2xl bg-white border border-slate-100 shadow-sm p-6">
              <p class="text-slate-400 text-xs font-bold uppercase tracking-widest mb-4">Autres services</p>
              <div class="flex flex-col gap-2">
                <RouterLink
                  v-for="s in otherServices"
                  :key="s.slug"
                  :to="`/services/${s.slug}`"
                  class="flex items-center justify-between px-4 py-3 rounded-xl border border-slate-100 hover:border-sky-200 hover:bg-sky-50 transition-colors group"
                >
                  <span class="flex items-center gap-2">
                    <span class="text-lg">{{ s.icon }}</span>
                    <span class="text-sm font-semibold text-slate-700 group-hover:text-sky-700">{{ s.title }}</span>
                  </span>
                  <svg class="w-4 h-4 text-slate-300 group-hover:text-sky-500 transition-colors" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7"/>
                  </svg>
                </RouterLink>
              </div>
            </div>

          </div>
        </div>

      </template>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ServiceDetailPage',
  data() {
    return {
      services: [
        {
          slug: 'reseau-telecom',
          title: 'Réseau Télécom',
          heading: 'Infrastructure Télécom de bout en bout',
          image: '/service/reseau-telecom.jpg',
          badgeBg: 'bg-cyan-50',
          badgeText: 'text-cyan-700',
          iconBg: 'bg-cyan-50',
          checkBg: 'bg-cyan-100',
          checkColor: 'text-cyan-600',
          borderColor: 'cyan-100',
          longDesc: "SYCOBE vous offre des services complets en réseau télécom : réseau de télévision, réseau informatique, Internet, réseau de téléphonie mobile, réseau téléphonique commuté, réseau numérique à intégration de services (RNIS) et le réseau Internet. Notre équipe dispose d'une expérience éprouvée dans le déploiement et la maintenance d'infrastructures télécom à l'échelle nationale.",
          bullets: [
            'Réseau de télévision',
            'Réseau de téléphonie mobile',
            'Réseau téléphonique commuté (RTC)',
            'Réseau numérique RNIS',
            'VSAT & liaisons FH',
            'Drive test & optimisation radio',
            'Traitement de CDR / RA',
            'Audit télécom & reporting',
            'Installation et mise en service',
          ]
        },
        {
          slug: 'reseau-informatique',
          title: 'Réseau Informatique',
          heading: 'Réseaux fiables et sécurisés',
          image: '/service/reseau-informatique.jpg',
          badgeBg: 'bg-blue-50',
          badgeText: 'text-blue-700',
          iconBg: 'bg-blue-50',
          checkBg: 'bg-blue-100',
          checkColor: 'text-blue-600',
          borderColor: 'blue-100',
          longDesc: "La société SYCOBE a la compétence dans le domaine réseau Informatique : étude du réseau, LAN, le câblage, Wifi, ADSL, Routeurs, Firewall, VPN et la sécurité, l'audite Informatique. Nous concevons et déployons des infrastructures réseau robustes pour les entreprises et institutions, en garantissant performance, disponibilité et sécurité.",
          bullets: [
            "Étude & conception LAN/WAN",
            "Câblage structuré",
            "Déploiement Wifi & ADSL",
            "Configuration routeurs & switches",
            "Firewall & filtrage",
            "VPN & accès distant sécurisé",
            "Segmentation réseau (VLAN)",
            "Audit sécurité réseau",
            "Audit informatique",
          ]
        },
        {
          slug: 'formations',
          title: 'Formations',
          heading: 'Montée en compétences de vos équipes',
          image: '/service/Formation.jpg',
          badgeBg: 'bg-green-50',
          badgeText: 'text-green-700',
          iconBg: 'bg-green-50',
          checkBg: 'bg-green-100',
          checkColor: 'text-green-600',
          borderColor: 'green-100',
          longDesc: "La société SYCOBE dispose d'un staff de formateurs expérimentés dans le domaine informatique et des partenaires connus dans la sous-région. Nos formations couvrent les langages de programmation, l'office, la maintenance, le réseau, la sécurité et la gestion des projets. Les programmes sont adaptés à vos équipes et dispensés en présentiel à Nouakchott ou Nouadhibou.",
          bullets: [
            "Langages de programmation",
            "Suite Office & bureautique",
            "Maintenance informatique",
            "Administration réseau",
            "Sécurité informatique",
            "Gestion de projets IT",
            "Ateliers pratiques & cas réels",
            "Coaching & suivi post-formation",
          ]
        },
        {
          slug: 'developpement',
          title: 'Développement',
          heading: 'Applications sur mesure pour votre métier',
          image: '/service/developpement.jpg',
          badgeBg: 'bg-purple-50',
          badgeText: 'text-purple-700',
          iconBg: 'bg-purple-50',
          checkBg: 'bg-purple-100',
          checkColor: 'text-purple-600',
          borderColor: 'purple-100',
          longDesc: "La société SYCOBE dispose d'un groupe de développeurs utilisant les outils des nouvelles technologies, et des partenaires connus dans la sous-région. Nous développons des applications métier sur mesure, des sites web et des systèmes de gestion adaptés aux besoins spécifiques de nos clients, via J2EE, MySQL, Oracle, PHP et Visual Basic.",
          bullets: [
            "Applications web J2EE & PHP",
            "Bases de données MySQL & Oracle",
            "Solutions Visual Basic",
            "Sites web & portails",
            "Systèmes de gestion métier",
            "CRM & ERP sur mesure",
            "Intégration & API",
            "Maintenance corrective & évolutive",
          ]
        },
      ],
    }
  },
  computed: {
    slug() {
      return String(this.$route.params.slug || '').toLowerCase()
    },
    service() {
      return this.services.find(s => s.slug === this.slug) || null
    },
    otherServices() {
      if (!this.service) return this.services
      return this.services.filter(s => s.slug !== this.service.slug)
    },
  },
}
</script>