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

header {
  padding: 10px 0px;
  background-color: var(--bg-header);
}

  .logo {
    width: 50px;
  }
</style>
