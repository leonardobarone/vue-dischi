<template>
  <header>
    <div class="container-fluid">
      <div class="row align-items-center">
        <div class="col-6">
          <img class="logo" :src="img" alt="">
        </div>
        <div class="col-6 text-end">
          <select v-model="genere" @change="$emit('filterGenre', genere)" name="genre" id="genre">
            <option value="all">All</option>
            <option v-for="(genre,index) in genres" :value="genre" :key="index">{{genre}}</option>
          </select>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    img: String,
    genres: Array
  },
  data() {
    return {
      genere: ""
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>

header {
  padding: 10px 0px;
  background-color: var(--bg-header);
}

  .logo {
    width: 50px;
  }
</style>
