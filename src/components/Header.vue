<template>
  <header>
    <div class="container-fluid">
      <div class="row">
        <div class="col-12">
          <img class="logo" src="../assets/images/spotify-logo.png" alt="">
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    img: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  .logo {
    width: 50px;
  }
</style>
