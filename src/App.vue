<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
const endpointType = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons/types1'
import AppMain from './components/AppMain.vue'
import { store } from './assets/data/store'

export default {
  name: 'App',
  components: { AppMain },

  // ARRAY POKEMON IN STORE
  created() {
    axios.get(endpoint).then(res => {
      store.pokemon = res.data.docs
    })
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
    <header>


    </header>


    <!--MAIN-->
    <AppMain />
  </div>
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>
