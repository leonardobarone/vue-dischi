<template>
  <div class="albums container">
    <div class="row row-cols-2 row-cols-md-5">
      <div class="col" v-for="(album, index) in albums" :key="index">
        <div class="album">
          <img class="poster" :src="album.poster" :alt="`${album.title} poster-img`">
          <h2 class="title">{{album.title.toUpperCase()}}</h2>
          <div class="author">{{album.author}}</div>
          <div class="year">{{album.year}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Albums',
  data() {
    return {
      albums:[]
      }
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then((response)=> {
        this.albums = response.data.response;
        console.log(this.albums)
    });
  } 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

   .row {
     --bs-gutter-x: 0rem;
   }

   .albums.container {
     padding-bottom: 2rem;
   }

  .album {
    text-align: center;
    background-color: var(--bg-header);
    padding: .3125rem .3125rem 3.1875rem .3125rem;
    margin: 2rem 1.5rem 0rem 1.5rem;
  }

  .poster {
    padding: 1.25rem 0rem;
    width: 80%;
  }

  .title {
    color: white;
    font-size: 1rem;
  }

  .author,
  .year {
    color: gray;
    font-size: .875rem;
  }

</style>
