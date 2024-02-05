<script>
import AppPokemonCard from './AppPokemonCard.vue'
import { store } from '../assets/data/store'

export default {
    name: 'AppMain',
    data: () => ({ store }),
    components: { AppPokemonCard },
}

</script>

<template>
    <main>
        <section id="pokemon-list">
            <div class="row card-container p-4">
                <div class="col-" v-for=" pokemon in store.pokemon">
                    <AppPokemonCard :name="pokemon.name" :image="pokemon.imageUrl" :number="pokemon.number"
                        :type="pokemon.type1" />
                </div>
            </div>
        </section>
    </main>
</template>

<style lang="scss"></style>