<template>
  <div id="search" v-bind:class="{ shrink: stickToTop }">
    <input
      autofocus
      v-model="obj.message"
      type="text"
      @keyup.enter="$emit('translate', obj.message)"
    >
    <button v-on:click="$emit('translate', obj.message)"></button>
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  props: {
    stickToTop: Boolean
  },
  data: () => {
    return {
      obj: {
        message: ""
      }
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
  font-size: 40px;
}

.stickToTop #search {
  margin-left: 50px;
}

input {
  margin-right: 10px;
  width: 200px;
  background-color: transparent;
  border: none;
  border-bottom: 1px solid grey;
}

.stickyToTop input {
  margin-right: 20px;
}

button {
  background-image: url("../assets/monkey.png");
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
