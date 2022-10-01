<script setup lang="ts">

import { supabase } from "../supabase";
import { ref } from "@vue/reactivity"
import Card from "../components/card.vue";

console.log("supabase :", supabase);

const maisons = [supabase];

let { data: Maison, error } = await supabase
    .from('Maison')
    .select('*')

console.log("Maison : ", Maison);

const user = ref(supabase.auth.user());

supabase.auth.onAuthStateChange(() => {
    user.value = supabase.auth.user()
})

</script>
        
    
<template>
    <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(420px,420px))] justify-around py-8 mr-40">
        <div v-for ="Maisons in Maison" :key="Maisons.nom">
            <Card v-bind="Maisons"></Card>
        </div>
    </div>
    <Suspense>
      <template #fallback>
        Loading...
      </template>
    </Suspense>
</template>
