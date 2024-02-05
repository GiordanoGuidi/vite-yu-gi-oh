<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons'
export default {
  name: 'App',
  data: () => ({
    pokèmon: []
  })

  ,
  created() {
    axios.get(endpoint).then(res => {
      this.pokèmon = res.data.docs
      console.log(this.pokèmon)

    })
  }

}

</script>

<template>
  <div class="container">
    <div class="row card-container">
      <div class="pokemon-card" v-for="pokèmon in pokèmon">
        <img :src="pokèmon.imageUrl" alt="" class="img-fluid rounded-circle">
        <div>{{ pokèmon.number }}</div>
        <div>{{ pokèmon.name }}</div>
        <div>{{ pokèmon.type1 }}</div>
      </div>




    </div>

  </div>
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>
