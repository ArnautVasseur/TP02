<template>
    <div class="w-96 flex flex-col relative m-auto pt-40 gap-6">
        <RouterLink to="/simple">
            <span class="relative p-5 flex justify-center border-[#55BC9F] border-2 dark:text-white dark:hover:border-white dark:hover:text-[#55BC9F] hover:text-[#55BC9F] hover:border-black dark:bg-[#222]">Simple</span>
        </RouterLink>
        <RouterLink to="/liste">
            <span class="relative p-5 flex justify-center border-[#55BC9F] border-2 dark:text-white dark:hover:border-white dark:hover:text-[#55BC9F] hover:text-[#55BC9F] hover:border-black dark:bg-[#222]">Liste</span>
        </RouterLink>
        <RouterLink to="/liste-fetch">
            <span class="relative p-5 flex justify-center border-[#55BC9F] border-2 dark:text-white dark:hover:border-white dark:hover:text-[#55BC9F] hover:text-[#55BC9F] hover:border-black dark:bg-[#222]">Liste-Fetch</span>
        </RouterLink>
        <RouterLink to="/liste-supabase">
            <span class="relative p-5 flex justify-center border-[#55BC9F] border-2 dark:text-white dark:hover:border-white dark:hover:text-[#55BC9F] hover:text-[#55BC9F] hover:border-black dark:bg-[#222]">Liste-Supabase</span>
        </RouterLink>
        <RouterLink to="/authentification">
            <span class="relative p-5 flex justify-center border-[#55BC9F] border-2 dark:text-white dark:hover:border-white dark:hover:text-[#55BC9F] hover:text-[#55BC9F] hover:border-black dark:bg-[#222]">Authentification</span>
        </RouterLink>
        <RouterLink to="/0">
            <span class="relative p-5 flex justify-center border-[#55BC9F] border-2 dark:text-white dark:hover:border-white dark:hover:text-[#55BC9F] hover:text-[#55BC9F] hover:border-black dark:bg-[#222]">Première Offre</span>
        </RouterLink>
    </div>
</template>