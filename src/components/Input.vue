<template>
  <div id="search">
    <input
      autofocus
      v-model="message"
      type="text"
      @keyup.enter="$emit('translate', message)"
    >
    <button v-on:click="$emit('translate', message)"></button>
  </div>
</template>

<script>
export default {
  name: 'Input',
  props: {
    stickToTop: Boolean
  },
  data: () => {
    return {
      message: ""
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#search {
  display: flex;
  flex-direction: row;
  align-items: center;
}

#search * {
  font-size: 30px;
}

input {
  margin-right: 10px;
  width: 200px;
  background-color: transparent;
  border: none;
  border-bottom: 1px solid grey;
}

button {
  background-image: url("~../assets/monkey.png");
  background-repeat: no-repeat;
  background-size: contain;
  background-color: transparent;
  height: 50px;
  width: 50px;
  border: none;
  cursor: pointer;
}

button:hover {
  opacity: 0.6;
}
</style>
