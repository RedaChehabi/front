<script setup>
  import { RouterView } from 'vue-router'
  import NavBar from './components/NavBar.vue';
  import FooterSection from './components/FooterSection.vue';
</script>

<template>
  <div>
    <NavBar/>
    <RouterView />
    <FooterSection />
  </div>

</template>
