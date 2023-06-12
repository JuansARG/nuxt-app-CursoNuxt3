<script setup lang="ts">
import type { Product } from '../interfaces/products';

const props = defineProps<{
    product: Product
}>();
</script>
<template>
    <div class="card" style="width: 18rem;">
        <img :src="props.product.thumbnail" class="card-img-top">
        <div class="card-body d-flex flex-column">
            <h5 class="card-title">{{ props.product.title }}</h5>
            <p class="card-text">{{ props.product.description }}</p>
            <a href="#" class="btn btn-primary mt-auto w-50">${{ props.product.price }}</a>
        </div>
    </div>
</template>
<style scoped>
.card {
    height: 400px;
}
.card-img-top {
    overflow: hidden;
    height: 50%;
    border-bottom: 2px solid black;
}
</style>