<script setup>

import CartItem from './subCartListItem.vue'

</script>

<template>

<div class="flex flex-1 flex-col gap-5 ">

<CartItem
    image="/sneakers/sneakers-1.jpg"
    title="asadsadsa sdsa dsa dsa dsa dsad"
    :price="12000"
/>
<CartItem/>
<CartItem/>
<CartItem/>
<CartItem/>

</div>
    

</template>