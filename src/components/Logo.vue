<template>
  <img v-bind:class="{ shrink: stickToTop }" src="../assets/logo.png">
</template>

<script>
export default {
  name: 'Logo',
  props: {
    stickToTop: Boolean
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
img {
  margin-bottom: 20px;
  height: auto;
  width: auto;
  transition: width 0.5s;
}

.shrink {
  margin-bottom: 0;
  margin-left: 100px;
  height: 70px;
}
</style>
