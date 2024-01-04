<script setup>

import TheHeader from './components/TheHeader.vue';
import TheCart from './components/subcomponents/subCard.vue'

</script>

<template>

<div class="w-4/5 m-auto bg-white rounded-xl shadow-xl my-14">
    
    <TheHeader />

    <div class="p-10">
    
        <h2  class="text-3xl font-semibold uppercase">Products</h2>

        <div class="grid grid-cols-4 gap-5 mt-8 max-md:grid-cols-1">
            <TheCart/>
            <TheCart/>
            <TheCart/>
            <TheCart/>
            <TheCart/>
            <TheCart/>
            <TheCart/>
        </div>

    </div>

    </div>

</template>



