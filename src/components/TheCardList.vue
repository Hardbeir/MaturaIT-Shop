<script setup>

    import Cart from './subcomponents/subCard.vue'

    const onClickAdd = () => {
        alert('add')
    }

    const onClickFavorite = () => {
        alert('Favorite')
    }

defineProps({
    products: Array
});

</script>

<template>
        <div class="grid grid-cols-4 gap-5 mt-8 max-md:grid-cols-1">

            <Cart 
                v-for="item in products"
                :key="item.id"
                :image="item.image" 
                :title="item.title" 
                :price="item.price"
                :rating="item.price - item.rating.rate"
                :onClickAdd="onClickAdd"
                :onClickFavorite = "onClickFavorite"
                :isFavorite="item.isFavorite"
            />

        </div>
</template>