<script setup lang="ts">
import {
    Disclosure,
    DisclosureButton,
    DisclosurePanel,
} from '@headlessui/vue'
import groupBy from "lodash/groupBy";
import { supabase } from "../../supabase";
const { data, error } = await supabase.from("maisoninfo").select("*");
if (error) console.log("n'a pas pu charger la table quartiercommune :", error);
</script>
    
<template>
    <section class="flex flex-col">
        <h3 class="text-2xl">Liste des quartiers</h3>
        <ul>
            <li v-for="quartierObject in (data)">
                <RouterLink :to="{
                  name: 'quartier-id',
                  params: { id: quartierObject.libelle_Quartier },
                }">{{ quartierObject.libelle_Quartier }}</RouterLink>
            </li>
        </ul>
        <Disclosure v-for="(listeQuartier, libelle_Commune) in groupBy(
        data,
        'libelle_Commune'
        )" :key="libelle_Commune">
            <DisclosureButton label="libelle_Commune">
                Button
            </DisclosureButton>
            <DisclosurePanel>
                <ul>
                    <li v-for="quartierObject in listeQuartier" :key="quartierObject.libelle_Quartier"></li>
                </ul>
            </DisclosurePanel>
        </Disclosure>

    </section>
</template>