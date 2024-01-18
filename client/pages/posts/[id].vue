<template>
    <div class="mx-auto border-2 rounded-lg p-4 space-y-4">
        <h1 class="text-center">{{ post.data.attributes.title }}</h1>
        <p>{{ post.data.attributes.content }}</p>
    </div>
</template>

<script setup>
    const { id } = useRoute().params

    const url = 'http://localhost:1337/api/posts/' + id

    const { data: post } = await useFetch(url)

</script>

<style scoped>

</style>