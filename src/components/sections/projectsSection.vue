<template>
  <div>
    <h2 class="text-[22px] md:text-[44px] font-semibold mt-[40px] md:mt-[70px]">
      Наши проекты
    </h2>

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

      <div @click="yetProjects = !yetProjects" class="border-1 md:border-2 rounded-[100px] border-[#1f1f1f] mt-[26px] bg-[#1f1f1f] text-white text-center md:text-[30px] py-3 md:py-6">
        <span v-if="!yetProjects">Показать ещё</span> <span v-if="yetProjects">Скрыть</span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

let yetProjects = ref(false)
</script>
