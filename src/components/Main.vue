<template>
  <div class="main">
    <Logo :stickToTop="stickToTop" />
    <div>臺灣 => 大陸</div>
    <SearchBar
      :stickToTop="stickToTop"
      v-on:translate="$emit('translate', $event)"
    />
  </div>
</template>

<script>
import Logo from './Logo.vue'
import SearchBar from './SearchBar.vue'

export default {
  name: 'Main',
  props: {
    stickToTop: Boolean
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
