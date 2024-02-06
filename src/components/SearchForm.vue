<script>
// import { store } from '../assets/data/store'
export default {
    name: 'SearchForm',
    data: () => ({
        searchType: '',
        pokemonType: [
            "Bug",
            "Dark",
            "Dragon",
            "Electric",
            "Fairy",
            "Fighting",
            "Fire",
            "Flying",
            "Ghost",
            "Grass",
            "Ground",
            "Ice",
            "Normal",
            "Poison",
            "Psychic",
            "Rock",
            "Steel",
            "Water"
        ]

    }),
    emits: ['submit-serch-type'],
}
</script>

<template>
    <select class="form-select w-50" size="3" aria-label="size 3 select example" v-model="searchType">
        <option :value="pokemonType" v-for="pokemonType in pokemonType" @click="$emit('submit-serch-type', searchType)">{{
            pokemonType
        }}
        </option>
    </select>
</template>

<style></style>