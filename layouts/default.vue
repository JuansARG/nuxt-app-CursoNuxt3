<template>
    <Nabvar class="mb-2" />
    <div class="
        container 
        bg-success 
        text-white
        d-flex
        justify-content-center
        ">
        <slot/>
    </div>
</template>
<style scoped>
.container {
    padding: 1rem;
    min-height: 80vh;
    border: 2px solid black;
}
</style>