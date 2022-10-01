<script setup lang="ts">
import FormulaireAgent from "../../components/FormulaireAgent.vue";
defineProps<{
    id: string;
}>();
</script>

<template>
    <div class="p-2">
        <FormulaireAgent :id="id" />
    </div>
</template>