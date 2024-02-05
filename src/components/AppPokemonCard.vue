<script>
import { store } from '../assets/data/store'
export default {
    name: 'AppPokemonCard',
    data: () => ({ store })
}

</script>

<template>
    <div class="pokemon-card" v-for="pokemon in store.pokemon">
        <div>
            <img :src="pokemon.imageUrl" :alt="pokemon.name" class="img-fluid rounded-circle">
        </div>
        <div>{{ pokemon.number }}</div>
        <div>{{ pokemon.name }}</div>
        <div>{{ pokemon.type1 }}</div>
    </div>
</template>

<style></style>