<script setup>
    import {useRoute, RouterView} from "vue-router"
    import cars from "../data/cars.json"
    import ContactView from "./ContactView.vue"

    const route = useRoute()
    const car = cars.find(c => c.id === parseInt(route.params.id))
    // Busca en el array de coches, el coche cuyo id es el que llega en los params

</script>

<template>
    <div>
        <h1>Car view</h1>
        <p>{{car.name}}</p>
        <p>{{car.year}}</p>
        <p>{{car.price}}</p>
        <RouterView />
        <!-- RouterView hace visibles los componentes anidados en rutas -->
    </div>
</template>