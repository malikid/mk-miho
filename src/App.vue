<template>
  <div id="app">
    <Main
      :stickToTop="obj.stickToTop"
      v-on:translate="translate"
    />
    <ResultContainer :text="obj.result" />
  </div>
</template>

<script>
import Main from './components/Main.vue'
import ResultContainer from './components/ResultContainer.vue'

import db from './db.js'

export default {
  name: 'App',
  components: {
    Main,
    ResultContainer
  },
  data: () => {
    return {
      obj: {
        result: "",
        stickToTop: false
      }
    }
  },
  methods: {
    translate: function (msg) {
      this.obj.result = db[msg]
      this.obj.stickToTop = this.obj.result ? true : false
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
