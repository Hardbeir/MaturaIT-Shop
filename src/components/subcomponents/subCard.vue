<script setup>

defineProps({

    image: String,
    title: String,
    price: Number,
    rating: Number,

    isFavorite: Boolean,
    isAdded: Boolean,

    onClickFavorite: Function,
    onClickAdd: Function,

});



</script>

<template>

<div class="relative m-10 border border-slate-100 rounded-xl p-8 cursor-pointer 
 hover:-translate-y-2 hover:shadow-xl transition delay-75 ease-in-out">

    <img class="absolute top-8 left-8" @click="onClickFavorite" :src="!isFavorite ? '/like-1.svg' : '/like-2.svg'" alt="Like disabled">

    <img :src="image" alt="Sneaker"/>

    <p class="mt-2">{{ title }}</p>

    <div class="flex justify-between mt-5">
        
        <div class="flex flex-col">

            <span class="font-semibold text-slate-400">Price:</span>
            <span> {{ price }} $</span>
            <span class="font-semibold text-slate-400">Rating:</span>
            <span>{{ rating.toFixed(2) }} $</span>

        </div>

        <img @click="onClickAdd" :src="!isAdded ? '/plus.svg' : '/checked.svg'" alt="Plus"/>

    </div>
    
</div>

</template>