<template>
  <nav class="xl:w-[1280px] xl:m-auto max-xl:fixed left-0 right-0 top-0 max-xl:bg-white flex justify-between items-center text-white py-2 md:py-6 xl:py-10 px-2 md:px-7 xl:px-10 z-20">
    <div>
      <a href="#main">
        <img src="../../assets/icons/main_logo.svg" alt="" class="w-[50px] md:w-[85px] xl:w-[70px]">
      </a>
    </div>

    <div class="hidden xl:flex text-[20px] gap-17 text-black ">
      <div>
        <a href="#services">Услуги</a>
      </div>

      <div>
        <a href="#projects">Проекты</a>
      </div>

      <div>
        <a href="#about">О нас</a>
      </div>

      <div>
        <a href="#contacts">Контакты</a>
      </div>
    </div>

    <div class="flex flex-col md:flex-row text-[15px] md:text-[24px] xl:text-[20px] gap-1 md:gap-5 items-center">
      <div class="text-black">+7-999-999-99-99</div>
      <div class="bg-[#4F7A23] text-center text-white px-3 md:px-5 py-1.5 md:py-2 rounded-2xl md:rounded-4xl"><a href="tel:+79999999999">Позвонить</a></div>
    </div>

    <div v-if="!openMenu" @click="openMenu = !openMenu" class="animate-opacity xl:hidden">
      <svg width="30" height="22" viewBox="0 0 20 14" fill="none" xmlns="http://www.w3.org/2000/svg" class="md:w-[45px] md:h-[35px]">
        <path d="M1 1H19M1 7H19M1 13H19" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </div>

    <div v-if="openMenu" @click="openMenu = !openMenu" class="animate-opacity">
      <svg width="30" height="22" viewBox="0 0 26 25" fill="none" xmlns="http://www.w3.org/2000/svg" class="md:w-[45px] md:h-[35px]">
        <path d="M1 24L25 1M1 1L25 24" stroke="black" stroke-width="3" stroke-linecap="round"/>
      </svg>
    </div>

    <transition>
      <div v-if="openMenu" class="absolute right-2 top-20 md:top-38 text-[15px] md:text-[24px] flex flex-col items-end gap-1 md:gap-2 p-3 border-2 border-[#4F7A23] rounded-[20px] backdrop-blur-sm transition-opacity duration-500 animate-opacity">
        <div class="py-3 px-4 md:px-7 bg-[#4F7A23] rounded-3xl">
          <a href="#services">Услуги</a>
        </div>
        <div class="py-3 px-4 md:px-7 bg-[#4F7A23] rounded-3xl">
          <a href="#projects">Проекты</a>
        </div>
        <div class="py-3 px-4 md:px-7 bg-[#4F7A23] rounded-3xl">
          <a href="#about">О нас</a>
        </div>
        <div class="py-3 px-4 md:px-7 bg-[#4F7A23] rounded-3xl">
          <a href="#contacts">Контакты</a>
        </div>
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
