<template>
    <div class="p-6">
        <div class="mx-auto border-2 rounded-lg p-4 space-y-4 flex flex-col">
            <input v-model="title" type="text" placeholder="Заголовок">
            <textarea v-model="content" rows="10" cols="50" placeholder="Текст">
            </textarea>
            <button @click="addPost()">Добавить пост</button>
        </div>
    </div>
</template>

<script setup>
let title = ref('')
let content = ref('')


const addPost = async() => {

    const result = await fetch('http://localhost:1337/api/posts',{
        method:'POST',
        headers:{
            'Content-Type':'application/json'
        },
        body:JSON.stringify({
            data:{
                title: title.value,
                content: content.value
            }
        })
    })
    console.log(result.status)
}

</script>

<style scoped>

</style>