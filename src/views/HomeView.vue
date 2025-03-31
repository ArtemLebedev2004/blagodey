<template>
  <header id="" class="relative ">
    <navBar />
  </header>

  <section id="main" class="px-2 md:px-4 xl:px-10 xl:w-[1280px] m-auto">
    <mainSection />
  </section>

  <section id="projects" class="px-2 md:px-4 xl:px-10 xl:w-[1280px] m-auto relative z-0">
    <projectsSection />
  </section>

  <section id="services" class="px-2 md:px-4 xl:px-10 xl:w-[1280px] m-auto">
    <servicesSection />
  </section>

  <section id="about" class="px-2 md:px-4 xl:px-10 xl:w-[1280px] m-auto">
    <aboutSection />
  </section>

  <footer id="contacts" class="    m-auto" :class="idActive == 3 ? 'px-0 xl:bg-[#4F7A23]' : 'px-2 md:px-4 xl:px-10 xl:w-[1280px] mt-10 xl:mt-20'">
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

import eventBus from '@/eventBus';
import { ref } from 'vue';

let idActive = ref(null)

eventBus.on('idActive', (data) => {            // from aboutSection
  idActive.value = data.idActive
})
</script>

<style>
#main:before, #projects:before, #services:before, #about:before {
	display: block;
	content: "";
	height: 55px;
	margin: -55px 0 0;
}
</style>