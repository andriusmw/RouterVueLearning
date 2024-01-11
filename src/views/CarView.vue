<script setup>
    import {useRoute} from "vue-router"
    import cars from "../data/cars.json"

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
    </div>
</template>