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
        <img :src="image" :alt="name" class="rounded-circle">
        <div>{{ number }}</div>
        <div class="fw-bolder">{{ name }}</div>
        <div>{{ type }}</div>
    </div>
</template>

<style></style>