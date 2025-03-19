<template>
  <header class="relative">
    <navBar />
  </header>

  <section class="mx-2 md:mx-4">
    <mainSection />
  </section>

  <section class="mx-2  md:mx-4">
    <projectsSection />
  </section>

  <section class="mx-2  md:mx-4">
    <servicesSection />
  </section>

  <section class="mx-2  md:mx-4">
    <aboutSection />
  </section>

  <footer class="">
    <footerContacts />
  </footer>
</template>

<script setup>
import mainSection from '../components/sections/mainSection.vue';
import projectsSection from '../components/sections/projectsSection.vue';
import servicesSection from '../components/sections/servicesSection.vue';
import aboutSection from '../components/sections/aboutSection.vue';
import navBar from '@/components/structure/navBar.vue';
import footerContacts from '@/components/structure/footerContacts.vue';
</script>
