<template>
  <div class="albums container">
    <div class="row row-cols-2 row-cols-md-5">
       <div class="col" v-for="(album, index) in albumsFiltered" :key="index">
          <Album :album="album" />
       </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import Album from './Album.vue'

export default {
  name: 'Albums',
  data() {
    return {
      albums:[],
      genres: []
      }
  },
  props: ['genre'],
  components: {
    Album
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then((response)=> {
        this.albums = response.data.response;
        this.albums.forEach(
          (element) => {

            if (!this.genres.includes(element.genre)){
              this.genres.push(element.genre)
            }
        });
        this.$emit("arrayGenres", this.genres)
    });
  },
  computed: {
    albumsFiltered() {
      return this.albums.filter(
        (elm) => {
          if (this.genre == "all" ) {
            return true
          } else {
            return elm.genre.toLowerCase().includes(this.genre.toLowerCase())
          }
      })
    }
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

   .col {
     margin-bottom: 20px;
   }


</style>
