<script setup>
    import cars from "../data/cars.json"
    import { RouterLink } from 'vue-router'
</script>

<template>
    <div>
        <h1>Home View</h1>
        <div class="cars">
            <RouterLink v-for="car in cars" :key="car.id" :to="`/cars/${car.id}`">{{ car.name }}</RouterLink>
        </div>
    </div>
</template>

<style scoped>
    .cars {
        display: flex; 
    }

    .cars a {
        text-decoration: none;
        color: rgba(216, 210, 210, 0.5);
        width: 100%;
        box-shadow: 0 0 10px rgba(231, 228, 228, 0.5);
        margin: 10px;
    }
</style>