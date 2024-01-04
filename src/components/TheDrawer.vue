<script setup>

import DrawerHeader from './subcomponents/subDrawerHeader.vue'
import CartList from './subcomponents/subCartList.vue'

</script>

<template>

<div class="fixed top-0 left-0 h-full w-full bg-black z-10 opacity-70"></div>

<div class="fixed right-0 top-0 w-96 h-full z-20 bg-white p-8">

    <DrawerHeader/>

    <CartList/>

    <div class="flex flex-col gap-5 my-7">

        <div class="flex gap-2">
            <span>Summary:</span>
            <div class="flex-1 border-b border-dashed"></div>
            <span class="font-bold">12321 $</span>
        </div>

        <button disabled="" 
        class="bg-lime-500 w-full rounded-xl py-3 mt-6
        text-white hover:bg-lime-600 transition
        active:bg-lime-700 disabled:bg-slate-400
        cursor-pointer">Buy</button>
        
    </div>



</div>

</template>