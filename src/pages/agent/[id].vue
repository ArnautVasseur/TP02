<script setup lang="ts">
import FormulaireAgent from "../../components/FormulaireAgent.vue";
defineProps<{
    id: string;
}>();
</script>

<template>
    <div class="p-2 pt-32 ml-16">
        <FormulaireAgent :id="id" />
    </div>
</template>