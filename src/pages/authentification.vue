<script setup lang="ts">
    import { ref } from "@vue/reactivity";
    import { supabase, user } from "@/supabase";
    async function signIn(data, node) {
      const { user, error } = await (nvlUtilisateur.value
        ? supabase.auth.signUp(data)
        : supabase.auth.signIn(data));
      if (error) {
        console.error(error);
        node.setErrors([error.message]);
      }
    }
    const nvlUtilisateur = ref(false);
    </script>
    <template>
      <div class="flex justify-center mr-40 relative pt-32">
        <button v-if="user" @pointerdown="supabase.auth.signOut()">
          Se déconnecter ({{ user.email }})
        </button>
        <FormKit v-else type="form" :submit-label="nvlUtilisateur ? 'S\'inscrire' : 'Se connecter'" @submit="signIn"
          :config="{
                classes: {
                input: 'p-1 bg-[#222] text-white rounded border-gray-300 mb-3 shadow-sm border',
                label: 'text-white font-medium',
                },
          }">
          <FormKit name="email" label="Votre eMail" type="email" />
          <FormKit name="password" label="Mot de passe" type="password" />
          <formKit label="Nouvel utilisateur ?" name="nvlUtilisateur" type="checkbox" v-model="nvlUtilisateur" wrapper-class="flex" />
        </FormKit>
      </div>
    </template>