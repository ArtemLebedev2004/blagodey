<template>
  <nav class="fixed left-0 right-0 top-0 flex justify-between items-center text-white bg-[#1f1f1f] m-2 md:m-4 py-4 md:py-6 px-4 md:px-7 rounded-[100px]">
    <div class="flex text-[15px] md:text-[25px] gap-3 md:gap-5 items-center">
      <div>+7-999-999-99-99</div>
      <div class="bg-white text-black px-2 md:px-4 py-1.5 rounded-2xl md:rounded-4xl"><a href="tel:+79999999999">Позвонить</a></div>
    </div>

    <div @click="openMenu = !openMenu">
      <svg width="30" height="22" viewBox="0 0 20 14" fill="none" xmlns="http://www.w3.org/2000/svg" class="md:w-[45px] md:h-[35px]">
        <path d="M1 1H19M1 7H19M1 13H19" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </div>

    <transition>
      <div v-if="openMenu" class="absolute right-2 top-18 md:top-26 text-[15px] md:text-[25px] flex flex-col items-end gap-1 transition-opacity duration-500 animate-opacity">
        <div class="py-3 md:py-5 px-4 md:px-7 bg-[#1f1f1f] rounded-3xl">Услуги</div>
        <div class="py-3 md:py-5 px-4 md:px-7 bg-[#1f1f1f] rounded-3xl">Проекты</div>
        <div class="py-3 md:py-5 px-4 md:px-7 bg-[#1f1f1f] rounded-3xl">О нас</div>
        <div class="py-3 md:py-5 px-4 md:px-7 bg-[#1f1f1f] rounded-3xl">Контакты</div>
      </div>
    </transition>


  </nav>
</template>

<script setup>
import { ref } from 'vue';

let openMenu = ref(false)

</script>

<style>
.v-leave-from {
  opacity: 1;
}
.v-leave-to {
  opacity: 0;
}
</style>
