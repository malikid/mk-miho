<template>
  <div id="search">
    <input v-model="obj.message" type="text">
    <button v-on:click="$emit('translate', obj.message)">
      翻譯
    </button>
    <div>即時預測: {{ db[obj.message] }}</div>
  </div>
</template>

<script>
import db from '../db.js'

export default {
  name: 'SearchBar',
  props: {
    stickToTop: Boolean
  },
  data: () => {
    return {
      obj: {
        message: ""
      },
      db
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
