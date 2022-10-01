<script setup lang="ts">
import { supabase } from '@/supabase'
import { ref } from "@vue/reactivity";
import card from "@/components/card.vue";
import { label } from "@formkit/inputs";
import { useRouter } from "vue-router";
import groupBy from "lodash/groupBy";

const router = useRouter();
const maison = ref({});
const { data:Quartier, error } = await supabase.from("allquartier").select("*");
if (error) console.log("n'a pas pu charger la table quartiercommune :", error);

const { data:Agent, error: error2 } = await supabase.from("agents").select("*");
if (error) console.log("n'a pas pu charger la table Agent :", error);

const props = defineProps(["id"]);
if (props.id) {
    // On charge les données de la maison
    let { data, error } = await supabase
        .from("Maison")
        .select("*")
        .eq("code_Maison", props.id);
    if (error) console.log("n'a pas pu charger le table Maison :", error);
    else maison.value = (data as any[])[0];
}


async function upsertMaison(dataForm, node) {
    const { data, error } = await supabase.from("Maison").upsert(dataForm);
    if (error || !data) node.setErrors([error?.message])
    else {
        node.setErrors([]);
        router.push({ name: "edit-id", params: { id: data[0].code_Maison } });
    }
}




</script>


<template>

    <div class="flex flex-col-reverse lg:flex-row-reverse ml-20 lg:mr-56">
        <div class="p-2">
            <h2 class="text-2xl text-white mt-16 flex justify-center mr-56">Résultat (Prévisualisation)</h2>
            <card v-bind="maison" />
        </div>

        <div class="p-2 border-2 mt-20 bg-[#222] rounded-2xl w-72 justify-center flex m-auto mr-80 lg:mr-16">
            <div class="p-4 ">
                <FormKit @submit="upsertMaison" type="form" v-model="maison" :config="{
                classes: {
                input: 'p-1 bg-[#222] text-white rounded border-gray-300 mb-3 shadow-sm border',
                label: 'text-white font-medium',
                },
                }" :submit-attrs="{ classes: 
                   { input: 'border-2 bg-[#222] text-[#3eb1ce] border border-white p-3 rounded ',
                     label:''
                } }">
                    <FormKit name="nom" label="Nom" />
                    <FormKit name="adresse" label="Adresse" />
                    <FormKit name="nbrChambre" label="Nombre de lits" type="number" />
                    <FormKit name="nbrSDB" label="Nombre de salle de bain" type="number" />
                    <FormKit name="surface" label="Superficie en m²" type="number" />
                    <FormKit name="prix" label="Prix" type="number" />
                    <FormKit name="fav" label="Ajouter l'offre aux favoris" type="checkbox" wrapper-class="flex" />
                    <FormKit name="code_Quartier" label="Quartier" type="select">
                        <option value="">Choisir un quartier...</option>
                        <optgroup v-for="(listeQuartier, libelle_Commune) in groupBy(Quartier,'libelle_Commune')" :key="libelle_Commune" v-bind:label="libelle_Commune">
                            <option v-for="Quartier in listeQuartier" :key="Quartier.id" v-bind:value="Quartier.code_Quartier">{{Quartier.libelle_Quartier}}</option>
                        </optgroup>
                    </FormKit>
                    <FormKit name="id_agent" label="Agent" type="select">
                        <option value="">Choisir un agent...</option>
                        <option v-for="agent in Agent" :key="agent.id" v-bind:value="agent.id">{{agent.first_name}}</option>
                    </FormKit>
                </FormKit>
            </div>
        </div>
    </div>
</template>