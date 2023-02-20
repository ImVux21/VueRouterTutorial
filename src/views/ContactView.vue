<script setup>
    import { reactive } from 'vue'  
    import { useRoute } from 'vue-router'
    import carsData from '../data/cars.json'

    const route = useRoute()
    const cars = reactive(carsData)

    const car = cars.find(c => c.id === parseInt(route.params.carId))
</script>

<template>
    <div>
        <h1>
            Contact Information
        </h1>
        <p>{{ car.contact.dealer }}</p>
        <p>{{ car.contact.number }}</p>
    </div>
</template>