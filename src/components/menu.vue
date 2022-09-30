<template>
    <ul>
        <div class="text-black flex flex-col gap-10 mt-36 mr-5 fixed right-0">
            <router-link class="link text-[#3eb1ce] hover:w-56 hover:h-14 transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-xl" to="/simple">
                <code class="font-mono">Simple</code>
            </router-link>
            <router-link class="link text-[#3eb1ce] hover:w-56 hover:h-14 transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-xl" to="/liste">
                <code class="font-mono">Liste</code>
            </router-link>
            <router-link class="link text-[#3eb1ce] hover:w-56 hover:h-14 transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-xl" to="/liste-fetch">
                <code class="font-mono">Liste-Fetch</code>
            </router-link>
            <router-link class="link text-[#3eb1ce] hover:w-56 hover:h-14 transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-xl" to="/0">
                <code class="font-mono">Offre 1</code>
            </router-link>
            <router-link class="link text-[#3eb1ce] hover:w-56 hover:h-14 transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-xl" to="/edit/new">
                <code class="font-mono">Créer Offre</code>
            </router-link>
            <router-link class="link text-[#3eb1ce] hover:w-56 hover:h-14 transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-xl" to="/liste-supabase">
                <code class="font-mono">Liste-Supabase</code>
            </router-link>
            <router-link class="link text-[#3eb1ce] hover:w-56 hover:h-14 transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-xl" to="/authentification">
                <code class="font-mono">Authentification</code>
            </router-link>
            <router-link class="link text-[#3eb1ce] hover:w-56 hover:h-14 transition-all w-48 h-10 justify-center items-center flex border-2 border-white bg-[#222] no-underline hover:text-xl" to="/edit/id ">
                <code class="font-mono">Modifier</code>
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