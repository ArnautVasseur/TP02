<script setup lang="ts">
import { supabase } from '@/supabase'
import { ref } from "@vue/reactivity";
import card from "@/components/card.vue";
import { label } from "@formkit/inputs";
import { useRouter } from "vue-router";

const router = useRouter();
const agent = ref({});

const { data: Agent, error } = await supabase.from("agents").select("*");
if (error) console.log("n'a pas pu charger la vue agents :", error);



const props = defineProps(["id"]);
if (props.id) {
    // On charge les données de la maison
    let { data, error } = await supabase
        .from("agents")
        .select("*")
        .eq("first_name", props.id);
    if (error) console.log("n'a pas pu charger le table Agent :", error);
    else agent.value = (data as any[])[0];
}

async function upsertAgent(dataForm, node) {
    const { data, error } = await supabase.from("Agent").upsert(dataForm);
    if (error || !data) node.setErrors([error?.message])
    else {
        node.setErrors([]);
        router.push({ name: "agent-id", params: { id: data[0].id_agent } });
    }
}
</script>
    
<template>
    <FormKit @submit="upsertAgent" type="form" v-model="agent" :config="{
    classes: {
    input: 'p-1 bg-[#222] text-white rounded border-gray-300 mb-3 shadow-sm border',
    label: 'text-white font-medium',
    },
    }" :submit-attrs="{ classes: 
       { input: 'border-2 bg-[#222] text-[#3eb1ce] border border-white p-3 rounded hover:text-white hover:border-[#3eb1ce]',
         label:''
    } }">
        <FormKit name="first_name" label="first_name" />
        <FormKit name="last_name" label="last_name" />
        <FormKit name="id_agent" label="Agent" type="select">
            <option value="">Choisir un utilisateur...</option>
            <option v-for="agent in Agent" :key="agent.id" v-bind:value="agent.id_user">{{agent.id_user}}</option>
        </FormKit>
    </FormKit>
</template>