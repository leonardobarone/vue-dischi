<template>
    <div id="root">
      <Header :genres="genres" @filterGenre="filtraggio" :img="require('./assets/images/spotify-logo.png')" />
      <Albums @arrayGenres="stampaArray" :genre="option"/>
    </div>
</template>

<script>
import Header from './components/Header.vue'
import Albums from './components/Albums.vue'

export default {
  name: 'App',
  components: {
    Header,
    Albums
  },
  data() {
    return {
      option: "",
      genres: []
    }
  },

  methods: {
    filtraggio(option) {
      this.option = option
    },
    stampaArray(genre) {
      this.genres = genre
    }
  }
}
</script>

<style lang="scss">
  @import './assets/style/common';     
</style>
