<script setup lang="ts">
import type { Product } from '../interfaces/products';
import { ProductResponse } from '../interfaces/productsResponse';

const { data, pending } = await useFetch<ProductResponse>('https://dummyjson.com/products', {
    lazy: true,
    pick: ['products'],
});

const products = data.value?.products as Product[];

</script>
<template>
    <div class="d-flex flex-column">
        <h1 class="py-2">Page Products</h1>
        <h1 v-if="pending">Loading data...</h1>
        <div v-else class="d-flex flex-wrap gap-4 justify-content-center card-container">
            <Card
                :product="product"
                v-for="product in products"
                :key="product.id"
            />
        </div>
    </div>
</template>
