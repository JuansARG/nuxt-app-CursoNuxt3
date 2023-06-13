<script setup lang="ts">

definePageMeta({
    layout: 'authentication'
});

</script>
<template>
    <div class="container">
        <div class="row">
            <h1>My Account</h1>
            <div class="col-6 d-flex gap-2 align-items-start">
                <NuxtLink to="/account" active-class="active" class="btn btn-primary" >Login</NuxtLink>
                <NuxtLink to="/account/register" active-class="active" class="btn btn-primary" >Register</NuxtLink>
            </div>
            <div class="col-6">
                <NuxtPage />
            </div>
        </div>
    </div>
</template>