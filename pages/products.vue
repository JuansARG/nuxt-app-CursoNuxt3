<script setup lang="ts">
import type { Product } from '../interfaces/products';
import { ProductResponse } from '../interfaces/productsResponse';

const { data } = await useFetch<ProductResponse>('https://dummyjson.com/products');
const products = data.value?.products as Product[];

</script>
<template>
    <div class="d-flex flex-column">
        <h1 class="text-center">Page Products</h1>
        <div class="d-flex flex-wrap gap-3 justify-content-center card-container">
            <Card
                :product="product"
                v-for="product in products"
                :key="product.id"
            />
        </div>
    </div>
</template>
