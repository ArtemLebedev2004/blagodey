<template>
  <div class="xl:w-[1280px] xl:m-auto flex flex-col gap-3 md:gap-5 items-center bg-[#4F7A23] text-white md:text-[30px] xl:text-[28px]  py-6 md:py-10 " :class="idActive == 3 ? 'm-0 rounded-none' : 'mt-[40px] md:mt-[65px] mb-2 md:mb-4 xl:mb-10 rounded-3xl md:rounded-[45px]'">
    <div>+7-999-999-99-99</div>

    <div>example@mail.ru</div>

    <div>г. Какой-то, ул. Какая-то, д. 1, кв. 1</div>

    <div class="flex gap-4 md:gap-6 mt-2 md:mt-4">
      <img src="../../assets/icons/vk.svg" alt="" class="md:w-14">
      <img src="../../assets/icons/tg.svg" alt="" class="md:w-14">

      <div @click="openModal = !openModal" class="bg-white py-2 px-4 md:px-8 text-[20px] md:text-[30px] text-[#4F7A23] font-semibold rounded-full">
        Заказать звонок
      </div>
    </div>


    <div class="bg-white w-[90%] h-[2px] mt-2 md:mt-4"></div>

    <div class="w-full mt-2 px-4 md:px-10 xl:px-15 text-[15px] md:text-[18px] xl:flex xl:justify-between">
      <div class="md:flex md:gap-8 md:max-xl:justify-center">
        <div><a href="" class="underline">Правила пользования интернет-сайтом</a></div>
        <div><a href="" class="underline">Политика конфиденциальности</a></div>
      </div>
      
      <div class="mt-2 md:mt-4 xl:mt-0 text-center">© 2025</div>
    </div>
  </div>

  <orderCallModal v-if="openModal" @closeModal="openModal = false" />
</template>

<script setup>
import eventBus from '@/eventBus';
import { ref } from 'vue';
import orderCallModal from '../modals/orderCallModal.vue';
// import { onMounted } from 'vue';
let idActive = ref(null)

eventBus.on('idActive', (data) => {            // from aboutSection
  idActive.value = data.idActive
})

let openModal = ref(false)
</script>
