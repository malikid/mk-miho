<template>
  <div class="main">
    <Logo />
    <div>繁體 => 簡體</div>
    <SearchBar />
  </div>
</template>

<script>
import Logo from './Logo.vue'
import SearchBar from './SearchBar.vue'

export default {
  name: 'Main',
  props: {
    msg: String
  },
  components: {
    Logo,
    SearchBar
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
