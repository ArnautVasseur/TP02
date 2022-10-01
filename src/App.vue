<script setup>
import menu_0 from "./components/menu.vue"
</script>

<template>
  <div :class="isDark ? 'dark' : ''">

    <body class="dark:bg-[#222]">
      <button class="button1 rounded-xl fixed top-[30px] right-[30px] bg-white dark:bg-[#222] p-5 w-[70px] border-2 border-white hover:border-black dark:border-transparent dark:hover:border-white" @click="menu = !menu">
        <span class="icon"><i class="fa-solid fa-bars fa-2xl dark:text-white"></i></span>
      </button>
      <div class="absolute mb-16 gap-3 flex top-[30px] left-[30px] items-center">
        <p class="relative text-lg dark:text-white">Dark Mode</p>
        <label class="switch relative dark:border-transparent dark:hover:border-white border-2 rounded-full ">
          <input type="checkbox" checked @click="isDark=!isDark">
          <span class="slider round bg-white before:bg-[#222] dark:before:bg-white"></span>
        </label>
      </div>
      <Transition>
        <menu_0 id="menu" class="mt-52" v-if="menu"></menu_0>
      </Transition>

      <Suspense>
        <template #fallback>
          Loading...
        </template>
        <router-view />
      </Suspense>
    </body>
  </div>
</template>

<style>

  .switch {
    width: 60px;
    height: 34px;
    box-shadow: 0 0px 25px rgba(255, 255, 255, 0.1);
  }
  
  .switch input { 
    opacity: 0;
    width: 0;
    height: 0;
  }
  
  .slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #ccc;
    -webkit-transition: .4s;
    transition: .4s;
    
  }
  
  .slider:before {
    position: absolute;
    content: "";
    height: 23px;
    width: 23px;
    left: 4px;
    bottom: 4px;
    background-color: white;
    -webkit-transition: .4s;
    transition: .4s;
  }
  
  input:checked + .slider {
    background-color: #222;
  }
  
  input:focus + .slider {
    box-shadow: 0 0 1px #222;
  }
  
  input:checked + .slider:before {
    -webkit-transform: translateX(26px);
    -ms-transform: translateX(26px);
    transform: translateX(26px);
  }
  
  .slider.round {
    border-radius: 34px;
  }
  
  .slider.round:before {
    border-radius: 50%;
  }
  
  .button1{
    box-shadow: 0 0px 25px rgba(255, 255, 255, 0.1);
    transition-duration: 300ms;
  }
  
  .button3{
    transition-delay: 300ms;
    opacity: 1;
  }
  
  .v-enter-active,
  .v-leave-active {
    transition: 0.6s ease-out;
  }
  
  .v-enter-from,
  .v-leave-to {
    opacity: 0;
    translate: 150px;
  }
  </style>

<script>
export default {
  data() {
    return {
      isDark: true,
      menu: true
    }
  },
  components: {

  }
}
</script>