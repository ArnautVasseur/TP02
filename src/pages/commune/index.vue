<script setup lang="ts">
  import { ref } from "@vue/reactivity";
import {
  Disclosure,
  DisclosureButton,
  DisclosurePanel,
} from '@headlessui/vue'
import groupBy from "lodash/groupBy";
import { supabase } from "../../supabase";
const { data, error } = await supabase.from("allcommunes").select("*");
if (error) console.log("n'a pas pu charger la table allcommunes :", error);

</script>
    
<template>
  <section class="flex flex-col ml-32 pt-16">
    <h3 class="text-2xl text-white my-16">Liste des communes</h3>
    <Disclosure>
      <DisclosureButton class="text-[#55BC9F] mr-40 mt-5 w-28 border border-white hover:text-white hover:border-[#55BC9F] transition-all"
        label="libelle_Commune">
        Villes
      </DisclosureButton>
      <DisclosurePanel>
        <ul>
          <li class="my-2 hover:underline" v-for="communeObject in (data)">
            <RouterLink class="text-white" :to="{
              name: 'commune-id',
              params: { id: communeObject.code_Commune },
            }">{{ communeObject.libelle_Commune }}</RouterLink>
          </li>
        </ul>
      </DisclosurePanel>
    </Disclosure>

  </section>
</template>

<script lang="ts">

</script>