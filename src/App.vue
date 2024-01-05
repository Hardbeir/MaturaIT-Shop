<script setup>
import { onMounted, ref, reactive } from 'vue'
import axios from 'axios'
import orderBy from 'lodash/orderBy'

// Importy komponentów
import TheHeader from './components/TheHeader.vue'
import TheCard from './components/TheCardList.vue'

// Obiekt filtra z właściwościami sortBy i searchQuery
const filters = reactive({
    sortBy: '',
    searchQuery: '',
});

// Ref na produkty
const products = ref([]);

let originalProducts = [];

// Funkcja sortująca produkty
const sortProducts = () => {
    let sortedProducts = [...originalProducts]; // Utworzenie kopii oryginalnej listy produktów

    if (filters.sortBy === 'title') {
        sortedProducts = orderBy(sortedProducts, 'title', 'asc');
    } else if (filters.sortBy === 'priceLow') {
        sortedProducts = orderBy(sortedProducts, 'price', 'asc');
    } else if (filters.sortBy === 'priceHigh') {
        sortedProducts = orderBy(sortedProducts, 'price', 'desc');
    }

    products.value = sortedProducts.filter(product => 
        product.title.toLowerCase().includes(filters.searchQuery.toLowerCase())
    );
}

// Funkcja do zmiany sortowania
const onChangeSelect = event => {
    filters.sortBy = event.target.value;
    sortProducts(); // Sortowanie po zmianie sortowania
}

// Funkcja do zmiany zapytania wyszukiwania
const onChangeInput = (event) => {
    filters.searchQuery = event.target.value;
    sortProducts(); // Sortowanie po zmianie zapytania wyszukiwania
}

// Funkcja pobierająca produkty
const fetchItems = async () => {
    try {
        const { data } = await axios.get('https://fakestoreapi.com/products');
        originalProducts = data;
        sortProducts(); // Sortowanie produktów po pobraniu
    } catch (err) {
        console.log(err);
    }
}

// Uruchomienie funkcji pobierającej produkty przy starcie komponentu
onMounted(fetchItems);

</script>

<template>
    <!-- <TheDrawer/> -->

<div class="w-4/5 m-auto bg-white rounded-xl shadow-xl my-14">
    
    <TheHeader/>

    <div class="p-10">

    <div class="flex justify-between items-center">

        <h2  class="text-3xl font-semibold uppercase">Products</h2>

        <div class="flex gap-4">

            <select @change="onChangeSelect" class="py-2 px-3 border rounded-md outline-none">
                        <option value="/">Sort</option>
                        <option value="title">Name</option>
                        <option value="priceLow">Price ++</option>
                        <option value="priceHigh">Price --</option>
                    </select>

        <div class="relative">

            <img class="absolute left-4 top-3" src="/search.svg" alt="Search" />

            <input @input="onChangeInput" class="border rounded-md py-2 pl-12 pr-4 outline-none focus:border-gray-400 " placeholder="Search...">
                   
        </div>

        </div>

    </div>

    <div class="mt-10">

        <TheCard :products="products" />

    </div>

    </div>

    </div>

</template>



