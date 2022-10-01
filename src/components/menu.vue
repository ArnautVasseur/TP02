<template>
    <ul>
        <div class="text-black flex flex-col gap-6 mt-32 mr-5 fixed right-0">
            <router-link class="link text-[#3eb1ce] hover:border-[#3eb1ce] transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-white" to="/simple">
                <code class="font-mono">Simple</code>
            </router-link>
            <router-link class="link text-[#3eb1ce] hover:border-[#3eb1ce] transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-white" to="/liste">
                <code class="font-mono">Liste</code>
            </router-link>
            <router-link class="link text-[#3eb1ce] hover:border-[#3eb1ce] transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-white" to="/liste-fetch">
                <code class="font-mono">Liste-Fetch</code>
            </router-link>
            <router-link class="link text-[#3eb1ce] hover:border-[#3eb1ce] transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-white" to="/0">
                <code class="font-mono">Offre 1</code>
            </router-link>
            <router-link class="link text-[#3eb1ce] hover:border-[#3eb1ce] transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-white" to="/edit/new">
                <code class="font-mono">Créer Offre</code>
            </router-link>
            <router-link class="link text-[#3eb1ce] hover:border-[#3eb1ce] transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-white" to="/liste-supabase">
                <code class="font-mono">Liste-Supabase</code>
            </router-link>
            <router-link class="link text-[#3eb1ce] hover:border-[#3eb1ce] transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-white" to="/authentification">
                <code class="font-mono">Authentification</code>
            </router-link>
            <router-link class="link text-[#3eb1ce] hover:border-[#3eb1ce] transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-white" to="/edit/id ">
                <code class="font-mono">Modifier</code>
            </router-link>
            <router-link class="link text-[#3eb1ce] hover:border-[#3eb1ce] transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-white" to="/quartier/new ">
                <code class="font-mono">Créer quartier</code>
            </router-link>
        </div>
    </ul>
    <Suspense>
      <template #fallback>
        Loading...
      </template>
    </Suspense>

</template>

<style>

.link
{
    transition-delay: 50ms;
}

</style>