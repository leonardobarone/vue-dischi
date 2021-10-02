<template>
  <div class="albums container">
    <div class="row row-cols-2 row-cols-md-5">
       <div class="col" v-for="(album, index) in albums" :key="index">
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
      albums:[]
      }
  },
  components: {
    Album
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then((response)=> {
        this.albums = response.data.response;
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

   .col {
     margin-bottom: 20px;
   }


</style>
