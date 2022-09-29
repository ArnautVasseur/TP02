<script setup lang="ts">
    import Bed from "../components/icons/bed.vue";
    import Bath from "../components/icons/bath.vue";
    import Surface from "./icons/surface.vue";
    import HeartIcon from "../components/icons/heart.vue";
   
    defineProps({
      nom : {type: String, default:'Default'},
      prix: {type:Number, default:2800 },
      adresse: {type: String, default: ''},
      nbrChambre: {type:Number , default: 3 },
      nbrSDB: {type:Number , default: 2 },
      surface: {type:Number, default: 80},
      fav:{ type:Boolean, default: false},
      image:{type:String, default:'src/assets/house1.jpg'}
      });

</script>

<template>
  <div>
     <figure class="flex flex-col mt-12 mx-8 w-96">
    <img
      :src=image
      alt="house"
      class="rounded-t-lg w-full h-48 object-cover"
    />
    <figcaption
      class="
        flex
        w-full
        flex-col
        gap-4
        rounded-b
        border border-indigo-50
        py-7
        px-5
      "
    >
      <div class="flex justify-between">
        <div class="w-2/5">
          <div class="flex items-center">
            <p class="text-2xl font-bold text-indigo-500"></p>
            <span class="text-xs font-normal text-gray-900">{{prix}} /month</span>
          </div>
          <p class="text-2xl font-bold">{{nom}}</p>
        </div>
        <div
          class="
            flex
            h-12
            w-12
            items-center
            justify-center
            rounded-full
            border-2 border-indigo-100
          "
        >
          <HeartIcon class="h-6 stroke-indigo-500 text-transparent" :class="{'fill-indigo-500' :fav}"></HeartIcon>
        </div>
      </div>
      <p class="text-base font-normal text-gray-900">
        {{adresse}}
      </p>
      <div class="w-full border border-indigo-50"></div>
      <div class="flex justify-between">
        <div class="flex items-center gap-2">
          <bed class="h-5 stroke-indigo-500"></bed>
          <span class="text-xs text-gray-500">{{nbrChambre}} Beds</span>
        </div>
        <div class="flex items-center gap-2">
          <bath class="h-5 stroke-indigo-500"></bath>
          <span class="text-xs text-gray-500">{{nbrSDB}} Bathrooms</span>
        </div>
        <div class="flex items-center gap-2">
          <Surface class="h-5 stroke-indigo-500"></Surface>
          <span class="text-xs text-gray-500">{{surface}} m²</span>
        </div>
      </div>
    </figcaption>
  </figure>
</div>
  
</template>

