<template>
    <header class="bg-emerald-950 text-white shadow-xl w-full p-6 flex gap-2 justify-between relative">
        <nav class="space-x-2">
            <NuxtLink to="/" class="border-2 rounded p-1 hover:text-teal-100 hover:border-teal-100">Главная</NuxtLink>
            <NuxtLink to="/about" class="border-2 rounded p-1 hover:text-teal-100 hover:border-teal-100">О нас</NuxtLink>
            <NuxtLink to="/blog" class="border-2 rounded p-1 hover:text-teal-100 hover:border-teal-100">Блог</NuxtLink>
        </nav>
        
        <svg @click="togleMenuFunc" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5M12 17.25h8.25" />
        </svg>
        <div class="bg-emerald-950 text-white shadow-xl absolute -bottom-16 right-0 w-60 h-max p-2" v-show="togleMenu">
            <DropMenu />
        </div>

    </header>

    <main class="container bg-gray-100 mx-auto flex-auto">
        <slot />
    </main>

    <footer class="bg-emerald-950 text-white w-full p-6 flex gap-2 justify-center">
        <NuxtLink to="/" class="border-2 rounded p-1 hover:text-teal-100 hover:border-teal-100">Главная</NuxtLink>
        <NuxtLink to="/about" class="border-2 rounded p-1 hover:text-teal-100 hover:border-teal-100">О нас</NuxtLink>
    </footer>
</template>

<script setup>

let togleMenu = ref(false)

const togleMenuFunc = () => {
    togleMenu.value = !togleMenu.value;
}
</script>

<style scoped>

</style>