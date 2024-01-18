<template>
    <div class="mx-auto border-2 rounded-lg p-4 space-y-4">
        <h1 class="text-center">{{ post.attributes.title }}</h1>
        <p>{{ post.attributes.content }}</p>
        <NuxtLink :to="`/posts/${ post.id }`" class="text-sky-600">Читать полностью</NuxtLink>
        <button @click="basketStore.add(this.post)">ToBasket</button>
        <button @click="basketStore.remove(this.post)">FromBasket</button>
        <p>{{ basketStore.productsTotal }}</p>
    </div>
</template>

<script setup>
const { post } = defineProps(['post'])
const basketStore = useBasketStore();
</script>

<style scoped>
    button {
       border: 1px teal solid;
       border-radius: 5px;
       padding: 4px;
       margin-left: 4px;
    }
</style>