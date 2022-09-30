<script setup>
import menu_0 from "./components/menu.vue"
</script>

<template>
  <div :class="isDark ? 'dark' : ''">
    <div class="fixed top-5 h-5 w-20 right-5 z-10 text-[#3eb1ce]" @click="menu = !menu">
        <div 
        class=
        "relative 
        top-0 
        left-0
        w-20
        h-14 
        flex 
        justify-center 
        items-center 
        bg-[#222]
        border-white
        border-2
        cursor-pointer 
        before:content-['Menu']"><span></span></div>
    </div>
    <menu_0 v-if="menu"/>
    
    <Suspense>
      <template #fallback>
        Loading...
      </template>
      <router-view/>
    </Suspense>
    
  </div>
</template>

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