<script setup lang="ts">
import Bed from "../components/icons/bed.vue";
import Bath from "../components/icons/bath.vue";
import Surface from "./icons/surface.vue";
import HeartIcon from "../components/icons/heart.vue";

defineProps({
  nom: { type: String, default: 'Default' },
  prix: { type: Number, default: 2800 },
  adresse: { type: String, default: 'adresse_default' },
  nbrChambre: { type: Number, default: 3 },
  nbrSDB: { type: Number, default: 2 },
  surface: { type: Number, default: 80 },
  fav: { type: Boolean, default: false },
  image: { type: String, default: 'src/assets/house1.jpg' }
});

</script>

<template>
  <div>
    <figure class="flex flex-col mt-12 mx-8 w-96 dark:border-white rounded-lg border-2 border-black">
      <img :src=image alt="house" class="w-full h-48 object-cover rounded-md" />
      <figcaption class="flex w-full flex-col gap-4 py-7 px-5">
        <div class="flex justify-between">
          <div class="w-2/5">
            <div class="flex items-center">
              <p class="text-2xl font-bold text-[#55BC9F]"></p>
              <span class="text-xs font-normal dark:text-gray-200">{{prix}} /month</span>
            </div>
            <p class="text-2xl font-bold dark:text-white">{{nom}}</p>
          </div>
          <div
            class=" flex h-12 w-12 items-center justify-center rounded-full border-2 dark:border-indigo-100 border-black">
            <HeartIcon class="h-6 stroke-[#55BC9F] text-transparent" :class="{'fill-[#55BC9F]' :fav}"></HeartIcon>
          </div>
        </div>
        <p class="text-base font-normal dark:text-white">
          {{adresse}}
        </p>
        <div class="w-full border dark:border-indigo-50 border-black"></div>
        <div class="flex justify-between">
          <div class="flex items-center gap-2">
            <bed class="h-5"></bed>
            <span class="text-xs text-gray-500">{{nbrChambre}} Beds</span>
          </div>
          <div class="flex items-center gap-2">
            <bath class="h-5"></bath>
            <span class="text-xs text-gray-500">{{nbrSDB}} Bathrooms</span>
          </div>
          <div class="flex items-center gap-2">
            <Surface class="h-5"></Surface>
            <span class="text-xs text-gray-500">{{surface}} m²</span>
          </div>
        </div>
      </figcaption>
    </figure>
  </div>

</template>

