<script>
import AppPokemonCard from './AppPokemonCard.vue'
export default {
    name: 'AppMain',
    components: { AppPokemonCard },
}

</script>

<template>
    <main>
        <div class="row card-container p-4">
            <AppPokemonCard />
        </div>
    </main>
</template>

<style lang="scss"></style>