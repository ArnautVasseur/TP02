<script setup lang="ts">
  import { ref } from "@vue/reactivity";
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
  <section class="flex flex-col ml-32">
    <h3 class="text-2xl text-white my-16">Liste des quartiers</h3>
    <Disclosure v-for="(listeQuartier, libelle_Commune) in groupBy(
    data,
    'libelle_Commune'
    )" :key="libelle_Commune">
      <DisclosureButton class="text-[#3eb1ce] mr-40 mt-5 w-28 border border-white hover:w-40 hover:text-xl"
        label="libelle_Commune">
        {{libelle_Commune}}
      </DisclosureButton>
      <DisclosurePanel>
        <ul>
          <li v-for="quartierObject in (data)">
            <RouterLink class="text-white" :to="{
              name: 'quartier-id',
              params: { id: quartierObject.code_Quartier },
            }">{{ quartierObject.libelle_Quartier }}</RouterLink>
          </li>
        </ul>
      </DisclosurePanel>
    </Disclosure>

  </section>
</template>

<script lang="ts">

</script>