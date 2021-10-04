<template>
    <div id="root">
      <Header @filterGenre="filtraggio()" :img="require('./assets/images/spotify-logo.png')" />
      <Albums />
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
      option: ""
    }
  }, 
  methods: {
    filtraggio(option) {
      this.option = option
    }
  }
}
</script>

<style lang="scss">
  @import './assets/style/common';     
</style>
