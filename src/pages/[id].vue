<script setup lang="ts">
    import Maisons from '../assets/Maisons.json'
    import Card from '../components/card.vue'
    
    defineProps({
        id: String,
    })
</script>

<template>
    <div class="flex justify-center mr-40 py-16">
        <Card v-bind="Maisons[id]"></Card>
    </div>
</template>