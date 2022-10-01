<script setup lang="ts">
import { supabase } from '@/supabase'
import { ref } from "@vue/reactivity";
import card from "@/components/card.vue";
import { label } from "@formkit/inputs";
import { useRouter } from "vue-router";

const router = useRouter();
const quartier = ref({});
const { data: dataQuartier, error } = await supabase
  .from("allquartier")
  .select("*");
if (error) console.log("n'a pas pu charger la vue allquartier :", error);

const props = defineProps(["id"]);
if (props.id) {
    // On charge les données de la maison
    let { data, error } = await supabase
        .from("allquartier")
        .select("*")
        .eq("libelle_Quartier", props.id);
    if (error) console.log("n'a pas pu charger le table Quartier :", error);
    else quartier.value = (data as any[])[0];
}

async function upsertQuartier(dataForm, node) {
    const { data, error } = await supabase.from("Quartier").upsert(dataForm);
    if (error || !data) node.setErrors([error?.message])
    else {
        node.setErrors([]);
        router.push({ name: "quartier-id", params: { id: data[0].code_Quartier } });
    }
}
</script>

<template>
    <FormKit @submit="upsertQuartier" type="form" v-model="quartier" :config="{
    classes: {
    input: 'p-1 bg-[#222] text-white rounded border-gray-300 mb-3 shadow-sm border',
    label: 'text-white font-medium',
    },
    }" :submit-attrs="{ classes: 
                   { input: 'border-2 bg-[#222] text-[#55BC9F] border border-white p-3 rounded hover:text-white hover:border-[#55BC9F]',
                     label:''
                } }">
        <FormKit name="libelle_Quartier" label="libelle_Quartier" />
        <FormKit name="libelle_Commune" label="libelle_Commune" />
    </FormKit>
</template>