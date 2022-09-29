<script setup lang="ts">
    import Card from "../components/card.vue";
    const chercherMaisons = await fetch("src/assets/Maisons.json")
    const Maisons = await chercherMaisons.json()
</script>
        
    
<template>
    <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(420px,420px))] justify-around mb-5">
       <Card v-for="maison in Maisons" :key="maison" v-bind="maison"></Card>
    </div>
</template>
