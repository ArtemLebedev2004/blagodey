<template>
  <div>
    <div class="xl:flex xl:mt-8 xl:gap-15">
      <div class="xl:relative">
        <h1 class="text-[40px] md:text-[80px] xl:text-[64px] font-semibold mt-[100px] md:mt-[190px] xl:mt-0 leading-12 md:leading-20">
          Проекты «под ключ» для бизнеса и частных лиц
        </h1>
        
        <div class="hidden xl:block text-[28px] mt-5">
          Гарантия 1 год
        </div>

        <div @click="openModal = !openModal" class="hidden xl:block relative xl:absolute xl:bottom-0 xl:w-full z-10 text-[20px] md:text-[30px] bg-[#4F7A23] text-white rounded-4xl md:rounded-[100px]  mt-[18px] md:mt-[25px] xl:mt-0 text-center py-4 md:py-7">
          Заказать проект
        </div>
      </div>

      <div class="relative mt-[30px] md:mt-[45px] xl:mt-0 pl-[13px] md:pl-[30px] pb-[13px] md:pb-[30px]">
        <img src="../../assets/img/main_img.png" alt="" class="w-full">
        <div class="absolute rounded-[20px] md:rounded-[40px] border-5 md:border-10 border-[#4F7A23] top-[9px] md:top-[15px] right-[9px] md:right-[15px] left-0 bottom-0"></div>

        <!-- <img src="../../assets/img/main_img_tablet.png" alt="" class="hidden md:block"> -->
      </div>
    </div>
    

    <div class="xl:hidden text-center mt-[18px] md:mt-[25px] text-[20px] md:text-[30px]">
      Гарантия 1 год
    </div>
    
    <div @click="openModal = !openModal" class="xl:hidden relative z-10 text-[20px] md:text-[30px] bg-[#4F7A23] text-white rounded-4xl md:rounded-[100px]  mt-[18px] md:mt-[25px] text-center py-4 md:py-7">
      Заказать проект
    </div>
  </div>
  
  <OrderCallModal v-if="openModal" @closeModal='openModal = false'/>

</template>

<script setup>
import { ref } from 'vue';
import OrderCallModal from '../modals/orderCallModal.vue';

let openModal = ref(false)
</script>