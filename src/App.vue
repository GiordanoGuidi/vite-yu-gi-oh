<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import { store } from './assets/data/store'
import AppPokemonCard from './components/AppPokemonCard.vue'
export default {
  name: 'App',
  components: { AppPokemonCard },

  created() {
    axios.get(endpoint).then(res => {
      store.pokemon = res.data.docs


    })
  }

}

</script>

<template>
  <div class="container">
    <div class="row card-container p-4">
      <AppPokemonCard />
    </div>

  </div>
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>
