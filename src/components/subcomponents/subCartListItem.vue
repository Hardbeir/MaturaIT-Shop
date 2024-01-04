<script setup>

defineProps({

    image: String,
    title: String,
    price: Number

})

</script>

<template>

<div class="w-full flex items-center border border-slate-100 p-4 rounded-xl gap-4">

    <img class="w-16 " :src="image" alt="">

    <div class="flex flex-col">

        <p>{{ title }}</p>

        <div class=" flex justify-between mt-2">
            
            <b>{{ price }} $</b>

            <img class="opacity-40 hover:opacity-100 cursor-pointer transition" src="/close.svg" alt="">

        </div>

    </div>
    

</div>

</template>