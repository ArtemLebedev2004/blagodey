<template>

    <div @click="$emit('closeModal')" class="w-12 h-12 md:w-17 md:h-17 fixed z-40 top-36 md:top-30 xl:top-30 right-2 md:right-15 xl:right-55 bg-[#4F7A23] rounded-[10px] md:rounded-[14px] flex justify-center items-center">
      <svg width="30" height="22" viewBox="0 0 26 25" fill="none" xmlns="http://www.w3.org/2000/svg" class="md:w-12 md:h-9">
        <path d="M1 24L25 1M1 1L25 24" stroke="white" stroke-width="3" stroke-linecap="round"/>
      </svg>
    </div>

    <div class="fixed top-50 xl:top-30 inset-x-2 md:inset-x-15 xl:inset-x-75 p-7 xl:p-12 bg-[#4F7A23] z-40 rounded-[20px] md:rounded-[30px]">
        <div class="text-center text-white text-[20px] md:text-[30px] xl:text-[28px]">
            Заказ звонка
        </div>

        <form action="https://formspree.io/f/xblgawon" method="POST" class="mt-5 md:mt-8 text-[15px] md:text-[24px] xl:text-[20px]">
            <input type="text" name="Имя" required class="w-full border-2 xl:border-3 border-white rounded-full py-2 md:py-4 px-4 md:px-8 outline-none text-white" placeholder="Ваше имя">
            <input type="phone" name="Телефон" required class="w-full border-2 xl:border-3 border-white rounded-full py-2 md:py-4 px-4 md:px-8 mt-3 md:mt-5 outline-none text-white" placeholder="Ваш телефон">

            <div class="group mt-4 md:mt-8">
                <input id="check_circle" type="checkbox" class="hidden" required>
                
                <label for="check_circle" class="flex gap-3 md:gap-6 xl:gap-3 items-center">
                    <div class="w-4 h-4 md:w-8 md:h-8 xl:w-6 xl:h-6 rounded-full border-2 xl:border-3 border-white group-has-checked:bg-white"></div>

                    <div class="w-fit text-white leading-5 md:leading-7">Даю согласие на обработку своих персональных данных</div>
                </label>
            </div>

            <input type="submit" value="Заказать звонок" class="w-full py-2 md:py-4 text-center rounded-full bg-white mt-5 md:mt-10 text-[#4F7A23]">
        </form>

        <div>
            <img src="@/assets/icons/logo_bg.svg" alt="" class="w-24 md:w-50 -z-1 absolute right-0 bottom-0">
        </div>
    </div>   
    
    <div class="fixed inset-0 bg-gray-400/75 z-30"></div>
</template>

<script setup>

</script>