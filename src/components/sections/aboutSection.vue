<template>
  <div :class="idActive == 3 ? 'relative max-xl:h-[1497px] md:max-xl:h-[1707px] xl:h-[1129px] pt-4 mt-[40px] md:mt-[70px]' : 'pt-4 mt-[40px] md:mt-[70px]'">
    <div v-if="idActive == 3" class="absolute -z-1 top-0 -left-2 md:-left-4 -right-2 md:-right-4 xl:-inset-x-10">
      <img src="@/assets/img/owner.jpg" alt="" class="md:hidden">
      <img src="@/assets/img/owner_md.jpg" alt="" class="hidden md:max-xl:block">
      <img src="@/assets/img/owner_xl.jpg" alt="" class="hidden xl:block">
    </div>

    <div class="flex items-center gap-3 md:gap-6">
      <div>
        <img src="../../assets/icons/logo_left_head.svg" alt="" class="md:w-20 xl:w-15">
      </div>

      <h2 class="text-[40px] md:text-[80px] xl:text-[64px] font-semibold " :class="idActive == 3 ? 'text-white' : ''">
        О нас
      </h2>
    </div>

    <div class="relative mt-6 xl:hidden" :class="idActive == 3 ? 'text-white' : ''">
      <div @click="openAboutMenu = !openAboutMenu" class="flex gap-5 md:gap-7 items-center text-xl md:text-[30px] font-semibold">
        <div>
          {{ blocks[idActive - 1].head }}
        </div>

        <div>
          <svg width="17" height="9" viewBox="0 0 17 9" fill="none" xmlns="http://www.w3.org/2000/svg" class="md:w-6 md:h-4">
            <path d="M1 1L8.5 8L16 1" :stroke="idActive == 3 ? 'white' : 'black'" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
      </div>

      <div class="bg-[#4F7A23] h-[2px] md:h-[3px] md:mt-2"></div>

      <transition>
        <div v-if="openAboutMenu" class="absolute flex flex-col gap-2 md:gap-3 top-9 md:top-15 left-0 right-0 px-2 py-4 border-3 border-[#4F7A23] rounded-2xl transition-all duration-500 backdrop-blur-[4px] bg-white/50 animate-opacity">
          <template v-for="block in blocks" :key="block">
            <div v-if="!block.active" @click="changeBlock(block.id)" class="w-max text-xl md:text-[30px] text-white py-2 md:py-3 px-4 md:px-6 bg-[#4F7A23] rounded-3xl">{{block.head}}</div>
          </template>
        </div>
      </transition>
    </div>

    <div class="hidden xl:flex relative gap-20 mt-6 text-[28px]" :class="idActive == 3 ? 'text-white' : ''">
      <template v-for="block in blocks" :key="block">
        <div @click="changeBlock(block.id)" :class="block.active ? 'border-b-3 border-[#4F7A23]' : ''" class="pb-[2px]">
          {{ block.head }}
        </div>
      </template>

      <div class="absolute h-[3px] bg-gray-300 left-0 right-0 top-11 -z-1"></div>
    </div>

    <div v-if="idActive == 1" class="xl:hidden flex gap-8 md:gap-14 flex-col mt-8 md:mt-14 animate-opacity">
      <div v-for="advantage in advantages" :key="advantage" class="">
        <div>
          <div class="w-[60px] md:w-22 h-[60px] md:h-22 flex items-center justify-center text-[32px] md:text-[42px] text-[#4F7A23] text-center border-2 border-[#4F7A23] rounded-full m-auto">{{advantage.id}}</div>
        </div>

        <div>
          <div class="text-xl md:text-[30px] mt-[14px] md:mt-4 font-semibold">{{advantage.head}}</div>
          <div class="text-[15px] md:text-[24px] mt-1">{{advantage.text}}</div>
        </div>
      </div>
    </div>

    <div v-if="idActive == 1" class="hidden xl:flex justify-between gap-10 mt-14 animate-opacity">
      <div class="flex flex-col gap-10">
        <template v-for="advantage in advantages" :key="advantage">
          <div v-if="advantage.id < 4" class="flex gap-4">
            <div>
              <div class="w-18 h-18 flex items-center justify-center text-[42px] text-[#4F7A23] text-center border-2 border-[#4F7A23] rounded-full m-auto">{{advantage.id}}</div>
            </div>

            <div>
              <div class="text-[28px] font-semibold">{{advantage.head}}</div>
              <div class="text-[15px] text-[20px] mt-1">{{advantage.text}}</div>
            </div>
          </div>
        </template>
      </div>
      
      <div class="flex flex-col gap-10">
        <template v-for="advantage in advantages" :key="advantage">
          <div v-if="advantage.id > 3" class="flex gap-4">
            <div>
              <div class="w-18 h-18 flex items-center justify-center text-[42px] text-[#4F7A23] text-center border-2 border-[#4F7A23] rounded-full m-auto">{{advantage.id}}</div>
            </div>

            <div>
              <div class="text-[28px] font-semibold">{{advantage.head}}</div>
              <div class="text-[15px] text-[20px] mt-1">{{advantage.text}}</div>
            </div>
          </div>
        </template>
      </div>
    </div>
   
    <div v-if="idActive == 2" class="mt-8 md:mt-14 animate-opacity xl:flex xl:flex-row-reverse xl:justify-between xl:items-center">
      <div class="xl:w-[50%]">
        <img src="@/assets/icons/main_logo_big.svg" alt="" class="m-auto md:w-[400px]">
      </div>

      <div class="flex flex-col gap-3 md:gap-5 mt-8 md:mt-12 xl:mt-0 xl:w-[50%]">
        <div v-for="petal_text in petals_text" :key="petal_text" class="h-[118px] md:h-[150px] xl:h-[140px] flex items-center pl-[18px] md:pl-[35px] rounded-tr-[20px] rounded-bl-[20px] text-[15px] md:text-[24px] xl:text-[20px] odd:bg-[#4F7A23] odd:text-white even:bg-white even:border-2 border-[#4F7A23] ">{{petal_text.text}}</div>
      </div>
    </div>

    <div v-if="idActive == 3" class="mt-5 md:mt-10 animate-opacity xl:flex xl:gap-[354px] text-[15px] md:text-[24px] xl:text-[20px]">
      <div class="xl:w-[50%]">
        <div class="pl-[30px] md:max-xl:pl-[40px] py-3 md:max-xl:py-5 text-white rounded-full text-[15px] bg-[#4F7A23]">
          <div class="text-[20px] md:text-[30px] xl:text-[28px]">Сергей Анохин</div>
          <div class="text-[15px] md:text-[24px] xl:text-[20px]">Основатель и руководитель компании</div>
        </div>

        <div class="text-white mt-5 md:mt-7 ">
          Опыт работы с 2012 года в одной из ведущих строительных компаний Астрахани, где я прошёл путь от менеджера  по снабжению до заместителя директора по строительству.
        </div>

        <div class="text-white mt-5 md:mt-7">
          Этот опыт дал мне глубокое понимание всех этапов строительных процессов – от подбора материалов до организации работы крупных подрядных команд.
        </div>

        <div class="text-white mt-5 md:mt-7 flex flex-col gap-4 md:gap-3">
          <div>Экспертиза</div>

          <div class="flex gap-2 md:gap-4">
            <div>
              <div class="w-[15px] h-[15px] md:w-6 md:h-6 xl:w-5 xl:h-5  mt-1 md:mt-1.5 rounded-full border-2 md:border-3 border-[#4F7A23]"></div>
            </div>
            <div>Управление строительными процессами и командами</div>
          </div>

          <div class="flex gap-2 md:gap-4">
            <div>
              <div class="w-[15px] h-[15px] md:w-6 md:h-6 xl:w-5 xl:h-5  mt-1 md:mt-1.5 rounded-full border-2 md:border-3 border-[#4F7A23]"></div>
            </div>
            <div>Качественный подбор материалов и поставщиков</div>
          </div>

          <div class="flex gap-2 md:gap-4">
            <div>
              <div class="w-[15px] h-[15px] md:w-6 md:h-6 xl:w-5 xl:h-5  mt-1 md:mt-1.5 rounded-full border-2 md:border-3 border-[#4F7A23]"></div>
            </div>
            <div>Контроль сроков и стандартов качества</div>
          </div>

          <div class="flex gap-2 md:gap-4">
            <div>
              <div class="w-[15px] h-[15px] md:w-6 md:h-6 xl:w-5 xl:h-5  mt-1 md:mt-1.5 rounded-full border-2 md:border-3 border-[#4F7A23]"></div>
            </div>
            <div>Внимание к деталям и долговечности решений</div>
          </div>
        </div>
      </div>

      <div class="hidden xl:block xl:w-[50%] text-white mt-30">
        <div class="italic">
          « - Грязную работу можно делать чисто – и в процессе, и в результате. Главное – подходить к делу  с ответственностью и вниманием к деталям».
        </div>

        <div class="mt-30">
          Создавая компанию "Благодей", я руководствовался своей жизненной миссией — приносить пользу этому миру, жить по совести и выполнять свою работу с полной ответственностью.
        </div>

        <div class="mt-7">
          Эти ценности легли в основу проекта и стали определяющими подход к созданию качественных и значимых решений для общества.
        </div>
      </div>
      
    </div>

    <div v-if="idActive == 4" class="mt-5 md:mt-12 animate-opacity">
      <div>
        <img src="@/assets/img/diplom.png" class="rounded-[20px] md:rounded-[30px] md:w-[80%] xl:w-[60%] m-auto shadow-[0px_0px_7px_5px_rgba(0,0,0,0.3)]" alt="">
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import eventBus from '@/eventBus';

let openAboutMenu = ref(false)

let idActive = ref(1)

let blocks = [
  {
    id: 1,
    head: "Наши преимущества",
    active: true
  },
  {
    id: 2,
    head: "О компании",
    active: false
  },
  {
    id: 3,
    head: "Об основателе",
    active: false
  },
  {
    id: 4,
    head: "Благодарности",
    active: false
  }
]

function changeBlock(id) {
  blocks[idActive.value - 1].active = false
  blocks[id - 1].active = true
  idActive.value = blocks[id - 1].id
  openAboutMenu.value = false

  eventBus.emit('idActive', {'idActive': id }) // To footerContacts and to HomeView.footer
}

let advantages = [
  {
    id: 1,
    head: "Опыт работы с Топ-застройщиками жилой недвижимости в г. Астрахань",
    text: "реализовали тысячи м2 территорий благоустройства в жилых комплексах, значительно повысили качество жизни жителей, создали комфортные и функциональные пространства, а также укрепили репутацию компании как надежного партнера.",
  },
  {
    id: 2,
    head: "Предлагаем услуги «под ключ»",
    text: "наши заказчики не беспокоятся о закупке материалов, монтаже и уборке после завершения работ.",
  },
  {
    id: 3,
    head: "Гарантия 1 год",
    text: "позволяет заказчикам быть уверенными, что после выполнения работ, в случае возможно возникших дефектов или недостатков, они смогут обратиться  за бесплатной помощью.",
  },
  {
    id: 4,
    head: "Высококвалифицированные специалисты",
    text: "в команде работают люди, обладающие значительным опытом и знанием тонкостей своей профессии.",
  },
  {
    id: 5,
    head: "Эффективная внутренняя организация",
    text: "мы создали четкие стандарты работы и систему промежуточного контроля за выполнением задач. Это позволяет нам минимизировать временные  и финансовые затраты для наших клиентов.",
  }
]

let petals_text = [
  {
    text: "Компания БлагоДей, – мы не просто благоустраиваем участки, а действуем так, чтобы каждое пространство становилось удобным, долговечным и эстетичным"
  },
  {
    text: "Корень «БЛАГО» олицетворяет добро, положительные эмоции, полезное и созидательное для человека"
  },
  {
    text: "Корень «ДЕЙ» от слова «Действовать» подчеркивает активность, динамику, готовность качественно и незамедлительно работать"
  },
  {
    text: "Полное название «БЛАГОДЕЙ» архаично, традиционно и надежно, мы заложили в него смысл основательный подход» и «проверенность»"
  }
]
</script>