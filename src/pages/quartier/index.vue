<script setup lang="ts">
import {
    Disclosure,
    DisclosureButton,
    DisclosurePanel,
} from '@headlessui/vue'
import groupBy from "lodash/groupBy";
import { supabase } from "../../supabase";
const { data, error } = await supabase.from("allquartier").select("*");
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
                }">{{quartierObject.libelle_Commune}} - {{ quartierObject.libelle_Quartier }}</RouterLink>
            </li>
        </ul>
        <Disclosure v-for="(listeQuartier, libelle_Commune) in groupBy(
        data,
        'libelle_Commune'
        )" :key="libelle_Commune">
            <DisclosureButton label="libelle_Commune">
              {{libelle_Commune}}
            </DisclosureButton>
            <DisclosurePanel>
                <ul>
                    <li v-for="quartierObject in listeQuartier" :key="quartierObject.libelle_Quartier"></li>
                </ul>
            </DisclosurePanel>
        </Disclosure>

    </section>
</template>

<script lang="ts">

async function supprimerQuartier() {
  const { data, error } = await supabase
    .from("Quartier")
    .delete()
    .match({ code_Quartier: quartierObject.value.code_Quartier });
  if (error) {
    console.error(
      "Erreur à la suppression de ",
      quartierObject.value,
      "erreur :",
      error
    );
  } else {
    router.push("/quartier");
  }
}
</script>