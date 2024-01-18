<template>
    <div class="text-center">
        <h1>{{ num }}</h1>
        <button @click="num++">count</button>
    </div>
</template>

<script setup>

let title = 'Главная страница'
let num = ref(33)
// const myCount = () => {
//     num.value++
// }


</script>

<style scoped>

</style>