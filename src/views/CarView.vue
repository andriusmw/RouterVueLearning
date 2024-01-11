<script setup>
    import {useRoute, useRouter, RouterView} from "vue-router"
    import cars from "../data/cars.json"
    import ContactView from "./ContactView.vue"

    const route = useRoute()
    const router = useRouter()

    const carId = parseInt(route.params.id)

    const car = cars.find(c => c.id === carId)
    // Busca en el array de coches, el coche cuyo id es el que llega en los params

</script>

<template>
    <div>
        <h1>Car view</h1>
        <p>{{car.name}}</p>
        <p>{{car.year}}</p>
        <p>{{car.price}}</p>
        <button @click="router.push(`/cars/${carId}/contact`)">Click me for contact</button>
        <RouterView />
        <!-- RouterView hace visibles los componentes anidados en rutas -->
    </div>
</template>