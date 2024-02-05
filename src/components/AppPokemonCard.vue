<script>
import { store } from '../assets/data/store'
export default {
    name: 'AppPokemonCard',
    data: () => ({ store })
}

</script>

<template>
    <ul class="pokemon-card" v-for="pokemon in store.pokemon">
        <li>
            <img :src="pokemon.imageUrl" :alt="pokemon.name" class="img-fluid rounded-circle">
        </li>
        <li>{{ pokemon.number }}</li>
        <li>{{ pokemon.name }}</li>
        <li>{{ pokemon.type1 }}</li>
    </ul>
</template>

<style lang="scss"></style>