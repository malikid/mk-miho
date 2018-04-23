<template>
  <button
    v-on:click="onClick"
    @keyup.enter="onClick"
  >
    {{text}}
  </button>
</template>

<script>
export default {
  name: 'Button',
  props: {
    text: String,
    handler: Function
  },
  methods: {
    onClick: function() {
      this.handler()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
button {
  background-color: #00FFFF;
  padding: 10px;
  border: none;
  font-size: 25px;
  cursor: pointer;
}

button:hover {
  opacity: 0.6;
}
</style>
