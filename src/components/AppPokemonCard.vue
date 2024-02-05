<script>
import { store } from '../assets/data/store'
export default {
    name: 'AppPokemonCard',
    props: {
        name: String,
        image: String,
        number: Number,
        type: String
    }
}

</script>

<template>
    <div class="pokemon-card">
        <img :src="image" :alt="name" class="img-fluid rounded-circle">
        <div>{{ number }}</div>
        <div>{{ name }}</div>
        <div>{{ type }}</div>
    </div>
</template>

<style></style>