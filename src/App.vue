<template>
  <header class="flex justify-between items-center bg-gray-400 m-2 py-2 px-3 rounded-3xl">
    <div class="flex text-[12px] gap-2 items-center">
      <div>+7-999-999-99-99</div>
      <div class="bg-gray-500 px-2 py-1 rounded-2xl"><a href="tel:+79999999999">Позвонить</a></div>
    </div>

    <div @click="openMenu = !openMenu">
      <svg width="28" height="20" viewBox="0 0 20 14" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M1 1H19M1 7H19M1 13H19" stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </div>

    <div v-if="openMenu" class="absolute right-2 top-14 text-sm flex flex-col items-end gap-1">
      <div class="py-2 px-3 bg-gray-400 rounded-3xl">Услуги</div>
      <div class="py-2 px-3 bg-gray-400 rounded-3xl">Проекты</div>
      <div class="py-2 px-3 bg-gray-400 rounded-3xl">О нас</div>
      <div class="py-2 px-3 bg-gray-400 rounded-3xl">Контакты</div>
    </div>
  </header>

  <section class="mx-2 font-display">
    <h1 class="text-[20px] font-semibold">
      Ландшафтные проекты “под ключ” для бизнеса и общественных пространств
    </h1>

    <div>
      <img src="./assets/img/main_img.png" alt="">
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';

let openMenu = ref(false)
</script>

<style>


</style>