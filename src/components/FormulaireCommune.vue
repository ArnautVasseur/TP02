<script setup lang="ts">
    import { supabase } from '@/supabase'
    import { ref } from "@vue/reactivity";
    import card from "@/components/card.vue";
    import { label } from "@formkit/inputs";
    import { useRouter } from "vue-router";
    
    const router = useRouter();
    const commune = ref({});
    const { data: Commune, error } = await supabase
      .from("allcommunes")
      .select("*");
    if (error) console.log("n'a pas pu charger la vue allcommunes :", error);
    
    const props = defineProps(["id"]);
    if (props.id) {
        // On charge les données de la maison
        let { data, error } = await supabase
            .from("allcommunes")
            .select("*")
            .eq("libelle_Commune", props.id);
        if (error) console.log("n'a pas pu charger le table Commune :", error);
        else commune.value = (data as any[])[0];
    }
    
    async function upsertCommune(dataForm, node) {
        const { data, error } = await supabase.from("Commune").upsert(dataForm);
        if (error || !data) node.setErrors([error?.message])
        else {
            node.setErrors([]);
            router.push({ name: "commune-id", params: { id: data[0].code_Commune } });
        }
    }
    </script>
    
    <template>
        <FormKit @submit="upsertCommune" type="form" v-model="commune" :config="{
        classes: {
        input: 'p-1 bg-[#222] text-white rounded border-gray-300 mb-3 shadow-sm border',
        label: 'text-white font-medium',
        },
        }" :submit-attrs="{ classes: 
                       { input: 'border-2 bg-[#222] text-[#55BC9F] border border-white p-3 rounded hover:text-white hover:border-[#55BC9F]',
                         label:''
                    } }">
            <FormKit name="libelle_Commune" label="libelle_Commune" />
        </FormKit>
    </template>