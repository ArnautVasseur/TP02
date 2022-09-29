<script setup lang="ts">
    import Card from "../components/card.vue";
    const chercherMaisons = await fetch("src/assets/Maisons.json")
    const Maisons = await chercherMaisons.json()
</script>
        
    
<template>
<<<<<<< HEAD
    <div>
       <Card v-for="maison in Maisons" :key="maison" v-bind="maison"></Card>
=======
    <div class="flex items-center flex-col">
        <p>Liste avec fetch</p>
       <Card v-for="m in Maisons" :key="m" v-bind="m"></Card>
>>>>>>> 50f55225777ecc9888d9a852eacf00bd1f7d5b4a
    </div>
</template>
