<script setup lang="ts">
import type { Product } from '../interfaces/products';

interface Props {
    product: Product;
}
const props = defineProps<Props>();
const product = toRef(props, 'product');

</script>
<template>
    <div class="card" style="width: 18rem;">
        <img :src="product.thumbnail" class="card-img-top">
        <div class="card-body d-flex flex-column">
            <h5 class="card-title">{{ product.title }}</h5>
            <p class="card-text">{{ product.category }}</p>
            <p class="card-text">{{ product.description }}</p>
            <NuxtLink 
                class="btn btn-primary mt-auto w-50"
                :to="{ name: 'products-category-id', params: { id: product.id, category: product.category } }">
                Buy
            </NuxtLink>
        </div>
    </div>
</template>
<style scoped>
.card {
    height: 500px;
}

.card-img-top {
    height: 50%;
    border-bottom: 2px solid black;
}
</style>