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
<<<<<<< HEAD
    <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(450px,450px))] justify-around mb-5">
=======
    <div class="flex items-center flex-col">
        <h6>Liste supabase</h6>
>>>>>>> 50f55225777ecc9888d9a852eacf00bd1f7d5b4a
        <div v-for ="Maisons in Maison" :key="Maisons.nom">
            <Card v-bind="Maisons"></Card>
        </div>
    </div>
</template>
