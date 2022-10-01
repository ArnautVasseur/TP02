<script setup lang="ts">
import FormulaireCommune from "../../components/FormulaireCommune.vue";
defineProps<{
    id: string;
}>();
</script>

<template> 
    <div class="p-2 pt-32 ml-16">
        <FormulaireCommune :id="id" />
    </div>
</template>