<template>
  <nav>
      <ul>
          <div class=" hidden text-black lg:flex items-center space-x-6">
              <router-link class="text-black no-underline hover:text-indigo-400" to="/">
                <code class="font-mono">Accueil</code>
              </router-link>
              <router-link class="text-black no-underline hover:text-indigo-400" to="/simple">
                <code class="font-mono">Simple.vue</code>
              </router-link>
              <router-link class="text-black  no-underline hover:text-indigo-700" to="/liste">
                <code class="font-mono">Liste.vue</code>
              </router-link>
              <router-link class="text-black  no-underline hover:text-indigo-400" to="/liste-fetch">
                <code class="font-mono">Liste-Fetch</code>
              </router-link>
              <router-link class="text-black  no-underline hover:text-indigo-400" to="/offre/1">
                <code class="font-mono">Offre nbr1</code>
              </router-link>
              <router-link class="text-black  no-underline hover:text-indigo-400" to="/offre/2">
                <code class="font-mono">Offre nbr2</code>
              </router-link> 
              <router-link class="text-black  no-underline hover:text-indigo-400" to="/edit/new">
                <code class="font-mono">New.vue</code>
              </router-link>
              <router-link class="text-black  no-underline hover:text-indigo-400" to="/liste-supabase">
                <code class="font-mono">Liste-Supabase</code>
              </router-link>
              <router-link class="text-black  no-underline hover:text-indigo-400" to="/authentification">
                <code class="font-mono">Authentification</code>
              </router-link>
              <router-link class="text-black  no-underline hover:text-indigo-400" to="/edit/id ">
                <code class="font-mono">Edit</code>
              </router-link>
            </ul>
          </div>
      </div>
            <h4 class="text-xl">
      <Bars3Icon class="inline-block h-5 w-5 text-blue-500" />
      Naviguer à travers le menu
    </h4>
    <ul class="ml-8">
      <li>
        <router-link class="text-black no-underline hover:text-indigo-400" to="/">
          <code class="font-mono">Accueil</code>
        </router-link>
      </li>
      <li>
        <router-link class="text-black no-underline hover:text-indigo-400" to="/simple">
          
          <code class="font-mono">Simple.vue</code>
        </router-link>
      </li>
      <li>
        <router-link class="text-black  no-underline hover:text-indigo-700" to="/liste">
          <code class="font-mono">Liste.vue</code>
        </router-link>
      </li>
      <li>
        <router-link class="text-black  no-underline hover:text-indigo-400" to="/liste-fetch">
          <code class="font-mono">Liste-Fetch</code>
        </router-link>
      </li>
      <li>
        <router-link class="text-red-600 underline" to="/0">
          lien vers
          <code class="font-mono">/src/offre/nbr</code>
        </router-link>
      </li>
      <li>
        <router-link class="text-red-600 underline" to="/1">
          lien vers
          <code class="font-mono">/src/offre/nbr2</code>
=======
        <router-link class="text-black  no-underline hover:text-indigo-400" to="/offre/1">
          <code class="font-mono">Offre nbr1</code>
        </router-link>
      </li>
      <li>
        <router-link class="text-black  no-underline hover:text-indigo-400" to="/offre/2">
          <code class="font-mono">Offre nbr2</code>
>>>>>>> 50f55225777ecc9888d9a852eacf00bd1f7d5b4a
        </router-link>
      </li>
      <li>
        <router-link class="text-black  no-underline hover:text-indigo-400" to="/edit/new">
          <code class="font-mono">New.vue</code>
        </router-link>
      </li>

      <li>
        <router-link class="text-black  no-underline hover:text-indigo-400" to="/liste-supabase">
          <code class="font-mono">Liste-Supabase</code>
        </router-link>
      </li>

      <li>
        <router-link class="text-black  no-underline hover:text-indigo-400" to="/authentification">
          <code class="font-mono">Authentification</code>
        </router-link>
      </li>
      <li>
        <router-link class="text-black  no-underline hover:text-indigo-400" to="/edit/id ">
          <code class="font-mono">Edit</code>
        </router-link>
      </li>

    </ul>
          </div>
  </nav>

  <!-- Affiche les pages -->
  <Suspense>
    <router-view class="m-2 border-2 p-2" />
    <template #fallback>
      Loading...
    </template>
  </Suspense>
</template>

<script setup>
import {ref} from 'vue';
const menuVisible = ref(true);
</script>



