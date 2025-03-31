<template>
  <div>
    <div class="flex mt-[40px] md:mt-[70px] items-center gap-3 md:gap-6">
      <div>
        <img src="../../assets/icons/logo_left_head.svg" alt="" class="md:w-20 xl:w-15">
      </div>

      <h2 class="text-[40px] md:text-[80px] xl:text-[64px] font-semibold">
      Наши услуги
      </h2>
    </div>

    <div class="mt-[22px] md:mt-[28px] flex max-xl:flex-col xl:flex-wrap gap-2 md:gap-4 text-white">
      <div v-for="service in services" :key="service" class="relative xl:w-[380px] h-[172px] xl:h-[221px] flex items-end  bg-[#4F7A23] rounded-[20px] pl-5 pb-5">
        <div class="absolute right-0" :class="service.stylesDivImg">
          <img :src="service.img" alt="" :class="service.stylesImg">
        </div>

        <div class="">
          <div v-html="service.head" class="text-[20px] md:text-[30px] xl:text-[28px] font-semibold md:max-xl:w-full" :class="service.stylesHead">
          </div>

          <div class="md:text-[24px] xl:text-[20px]">
            {{service.text}}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// import { ref } from 'vue';

let services = [
  {
    head: "Укладка тротуарной плитки",
    text: "прочные и стильные дорожки",
    img: new URL('../../assets/icons/paving_slab.svg', import.meta.url).href,
    stylesHead: "w-[190px] xl:w-[270px]",
    stylesDivImg: "top-[18px]",
    stylesImg: "xl:w-[95px]"
  },
  {
    head: "Монтаж террас",
    text: "уютные зоны для отдыха",
    img: new URL('../../assets/icons/terrace.svg', import.meta.url).href,
    stylesHead: "w-[190px] xl:w-[220px]",
    stylesDivImg: "bottom-0",
    stylesImg: "xl:w-[91px]"
  },
  {
    head: "Системы водоотведения",
    text: "защита участка от влаги",
    img: new URL('../../assets/icons/tube.svg', import.meta.url).href,
    stylesHead: "w-[220px]",
    stylesDivImg: "top-0",
    stylesImg: "xl:w-[112px]"
  },
  {
    head: "Монтаж <br class='md:hidden'> зон отдыха и пергол",
    text: "создание уюта и эстетики",
    img: new URL('../../assets/icons/pergola.svg', import.meta.url).href,
    stylesHead: "w-[220px] xl:w-[270px]",
    stylesDivImg: "bottom-0",
    stylesImg: "xl:w-[71px]"
  },
  {
    head: "Вертикальное планирование участка",
    text: "подготовка территории",
    img: new URL('../../assets/icons/ruler.svg', import.meta.url).href,
    stylesHead: "w-[230px] xl:w-[350px]",
    stylesDivImg: "top-[18px]",
    stylesImg: "xl:w-[104px]"
  },
  {
    head: "Монтаж <br class='md:max-xl:hidden'> уличного освещения",
    text: "комфортные прогулки",
    img: new URL('../../assets/icons/flashlight.svg', import.meta.url).href,
    stylesHead: "w-[200px] xl:w-[280px]",
    stylesDivImg: "bottom-0",
    stylesImg: "xl:w-[121px]"
  },
]
</script>