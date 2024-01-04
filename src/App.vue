<script setup>

import { onMounted, ref } from 'vue'
import axios from 'axios'

import TheHeader from './components/TheHeader.vue'
import TheCard from './components/TheCardList.vue'
/* import TheDrawer from './components/TheDrawer.vue' */

const items = ref([]);

onMounted(async() => {

    try{
        const { data } = await axios.get('https://fakestoreapi.com/products')

        items.value = data;
        console.log(data)
    } catch (err){
        console.log(err)
    }

})

</script>

<template>
    <!-- <TheDrawer/> -->

<div class="w-4/5 m-auto bg-white rounded-xl shadow-xl my-14">
    
    <TheHeader/>

    <div class="p-10">

    <div class="flex justify-between items-center">

        <h2  class="text-3xl font-semibold uppercase">Products</h2>

        <div class="flex gap-4">

            <select class="py-2 px-3 border rounded-md outline-none">
            <option value="Name">Name</option>
            <option value="Price+">Price ++</option>
            <option value="Price-">Price --</option>
        </select>

        <div class="relative">

            <img class="absolute left-4 top-3" src="/search.svg" alt="Search" />

            <input class="border rounded-md py-2 pl-12 pr-4 outline-none focus:border-gray-400 " placeholder="Search...">

        </div>

        </div>

    </div>

    <div class="mt-10">

        <TheCard :items="items" />

    </div>

    </div>

    </div>

</template>



