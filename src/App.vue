<template>
  <nav>
      <ul>
          <div class="text-black lg:flex items-center space-x-6">
              <router-link class="text-black no-underline hover:text-indigo-400" to="/simple">
                <code class="font-mono">Simple.vue</code>
              </router-link>
              <router-link class="text-black  no-underline hover:text-indigo-700" to="/liste">
                <code class="font-mono">Liste.vue</code>
              </router-link>
              <router-link class="text-black  no-underline hover:text-indigo-400" to="/liste-fetch">
                <code class="font-mono">Liste-Fetch</code>
              </router-link>
              <router-link class="text-black  no-underline hover:text-indigo-400" to="/0">
                <code class="font-mono">Offre 1</code>
              </router-link>
              <router-link class="text-black  no-underline hover:text-indigo-400" to="/1">
                <code class="font-mono">Offre 2</code>
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
              </div>
            </ul>
  </nav>

  <Suspense>
    <router-view class="m-2 border-2 p-2" />
    <template #fallback>
      Loading...
    </template>
  </Suspense>
</template>



