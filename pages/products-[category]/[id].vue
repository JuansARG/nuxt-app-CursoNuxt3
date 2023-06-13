<script setup lang="ts">
import type { Product } from '../../interfaces/productsResponse';

definePageMeta({
    validate: route => {
        const regex = /^[0-9]+$/;
        const expresion = new RegExp(regex);
        const id = route.params.id;
        return expresion.test(id as string);
    }
});

const route = useRoute();
const { id, category } = route.params;
const { data: product } = await useFetch<Product>(`https://dummyjson.com/products/${ route.params.id }`);

</script>
<template>
    <div>
        <h1>Producto {{ id }}</h1>
        <p class="text-center">{{ product?.title }}</p>
        <p class="text-end">{{ category }}</p>
        <p>{{ product?.description }}</p>
        <p>${{ product?.price }}</p>
    </div>
</template>