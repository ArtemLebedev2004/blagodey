<template>
  <div>
    <div class="flex mt-[40px] items-center gap-3">
      <div>
        <img src="../../assets/icons/logo_left_head.svg" alt="">
      </div>

      <h2 class="text-[40px] md:text-[44px] font-semibold  md:mt-[70px]">
      Наши проекты
      </h2>
    </div>

    <div class="w-full mt-[22px] md:mt-[28px]">
      <img src="../../assets/img/project1.png" alt="" class="w-full">
      <img src="../../assets/img/project2.png" alt="" class="w-full mt-[8px] md:mt-[15px]">
      <img src="../../assets/img/project3.png" alt="" class="w-full mt-[8px] md:mt-[15px]">

      <div v-if="yetProjects">
        <img src="../../assets/img/project4.png" alt="" class="w-full mt-[8px] md:mt-[15px]">

        <div class="flex justify-between gap-[8px] md:gap-[15px] mt-[8px] md:mt-[15px]">
          <div>
            <img src="../../assets/img/project5.png" alt="" class="w-full">
          </div>

          <div>
            <img src="../../assets/img/project6.png" alt="" class="w-full">
          </div>
        </div>
      </div>

      <div @click="yetProjects = !yetProjects" class="border-1 md:border-2 rounded-[100px] border-[#4F7A23] mt-[26px] bg-[#4F7A23] text-white text-center text-[20px] md:text-[30px] py-3 md:py-6">
        <span v-if="!yetProjects">Показать ещё</span> <span v-if="yetProjects">Скрыть</span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

let yetProjects = ref(false)
</script>
