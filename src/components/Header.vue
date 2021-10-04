<template>
  <header>
    <div class="container-fluid">
      <div class="row align-items-center">
        <div class="col-6">
          <img class="logo" :src="img" alt="">
        </div>
        <div class="col-6 text-end">
          <select name="genre" id="genre">
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
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
