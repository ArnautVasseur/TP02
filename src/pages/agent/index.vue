<script setup lang="ts">
  import { ref } from "@vue/reactivity";
import {
  Disclosure,
  DisclosureButton,
  DisclosurePanel,
} from '@headlessui/vue'
import groupBy from "lodash/groupBy";
import { supabase } from "../../supabase";
const { data, error } = await supabase.from("agents").select("*");
if (error) console.log("n'a pas pu charger la table agents :", error);

</script>
    
<template>
  <section class="flex flex-col ml-32 pt-16">
    <h3 class="text-2xl dark:text-white my-16">Liste des agents</h3>
    <Disclosure>
      <DisclosureButton class="text-[#55BC9F] mr-40 mt-5 w-28 border dark:border-white border-black dark:hover:text-white hover:text-black dark:hover:border-[#55BC9F] hover:border-[#55BC9F] transition-all"
        label="libelle_Commune">
        Agents
      </DisclosureButton>
      <DisclosurePanel>
        <ul>
          <li class="my-2 hover:underline" v-for="agentobject in (data)">
            <RouterLink class="text-white" :to="{
              name: 'agent-id',
              params: { id: agentobject.id_agent },
            }">{{ agentobject.first_name }} - {{agentobject.last_name}}</RouterLink>
          </li>
        </ul>
      </DisclosurePanel>
    </Disclosure>

  </section>
</template>

<script lang="ts">

</script>