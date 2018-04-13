<template>
  <div class="container">
     大陸：{{text}}
   </div>
</template>

<script>
export default {
  name: 'ResultContainer',
  props: {
    text: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  padding-left: 150px;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: start;
  font-size: 50px;
}
</style>
