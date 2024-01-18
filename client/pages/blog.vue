<template>
    <div class="p-6 space-y-2">
        <CardPost v-for="item in posts?.data" :key="item.id" :post ="item" />
    </div>
</template>

<script setup>

const { data: posts } = await useFetch('http://localhost:1337/api/posts')

</script>

<style scoped>

</style>