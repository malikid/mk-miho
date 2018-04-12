<template>
  <div id="search">
    <input v-model="a.message" type="text">
    <button v-on:click="submit">搜尋</button>
    <div>大陸: {{ db[a.message] }}</div>
  </div>
</template>

<script>
import db from '../db.js'

export default {
  name: 'SearchBar',
  props: {
    msg: String
  },
  data: () => {
    return {
      a: {},
      db
    }
  },
  methods: {
    submit: function () {
      this.a.message = db[this.a.message]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
