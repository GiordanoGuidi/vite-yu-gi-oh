<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
const endpointType = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons/types1';
import AppMain from './components/AppMain.vue';
import SearchForm from './components/SearchForm.vue';
import { store } from './assets/data/store';

export default {
  name: 'App',
  components: { AppMain, SearchForm },
  methods: {
    //CHIAMATA API X VISUALIZZARE PRIMI 10 POKEMON
    fetchPokemon(endpoint) {
      axios.get(endpoint).then(res => {
        store.pokemon = res.data.docs;
      })
    },
    //CHIAMATA API IN BASE AL TIPO DI POKEMON
    searchTypes(searchType) {
      const searchEndpoint = `${endpoint}?eq[type1]=${searchType}`;
      this.fetchPokemon(searchEndpoint)
    },
  },

  // ARRAY POKEMON IN STORE
  created() {
    axios.get(endpoint).then(res => {
      store.pokemon = res.data.docs
    }),
      // ARRAY POKEMON TYPE IN STORE
      axios.get(endpointType).then(res => {
        store.type = res.data
      })
  }

}

</script>

<template>
  <div class="container">
    <!--HEADER-->
    <header class="d-flex justify-content-end mb-4">
      <SearchForm @submit-serch-type="searchTypes" @submit-all-pokemon="fetchPokemon" />
    </header>


    <!--MAIN-->
    <AppMain />
  </div>
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>
