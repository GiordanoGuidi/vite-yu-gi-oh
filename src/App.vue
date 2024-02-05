<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import AppMain from './components/AppMain.vue'
import { store } from './assets/data/store'

export default {
  name: 'App',
  components: { AppMain },

  created() {
    axios.get(endpoint).then(res => {
      store.pokemon = res.data.docs
    })
  }

}

</script>

<template>
  <div class="container">
    <AppMain />
  </div>
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>
