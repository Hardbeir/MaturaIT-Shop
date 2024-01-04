<script setup>

    import Cart from './subcomponents/subCard.vue'

    const onClickAdd = () => {
        alert('add')
    }

    const onClickFavorite = () => {
        alert('Favorite')
    }

defineProps({
    items: Array
})

</script>

<template>
        <div class="grid grid-cols-4 gap-5 mt-8 max-md:grid-cols-1">

            <Cart 
                v-for="item in items"
                :key="item.id"
                :image="item.image" 
                :title="item.title" 
                :price="item.price"
                :onClickAdd="onClickAdd"
                :onClickFavorite = "onClickFavorite"
            />

        </div>
</template>