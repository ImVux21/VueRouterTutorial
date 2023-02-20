<script setup>
    import { ref, reactive } from 'vue'
    import { useRoute, RouterView, useRouter } from 'vue-router'
    import carsData from '../data/cars.json'

    const route = useRoute()
    const router = useRouter()

    const cars = reactive(carsData)
    const car = cars.find(c => c.id === parseInt(route.params.carId))
</script>

<template>
    <div v-if="car">
        <h1>Car View</h1>
        <p>{{ car.name }}</p>
        <p>{{ car.year }}</p>
        <p>{{ car.price }}</p>
        <button @click="router.push(`/cars/${parseInt(route.params.carId)}/contact`)">Click me for contact</button>
        <RouterView />
    </div>
    <div v-else>
        <h1>Car not found</h1>
    </div>
</template>

