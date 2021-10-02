<template> 
     
        <div class="album">
          <img class="poster" :src="album.poster" :alt="`${album.title} poster-img`">
          <h2 class="title">{{album.title.toUpperCase()}}</h2>
          <div class="author">{{album.author}}</div>
          <div class="year">{{album.year}}</div>
        </div>
    
</template>

<script>

export default {
  name: 'Album',
  props: {
    album: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

   

  .album {
    height: 100%;
    text-align: center;
    background-color: var(--bg-header);
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
  .year,
  .title {
    padding: 0px calc(20%);
  }

  .author,
  .year {
    color: gray;
    font-size: .875rem;
  }

</style>
