<template>
  <div id="search">
    <input
      autofocus
      v-model="message"
      type="text"
      @keyup.enter="emitTranslate"
    >
    <Button text="我確定了！" :handler="emitTranslate" />
  </div>
</template>

<script>
import Button from "./Button.vue"

export default {
  name: 'Input',
  components: {
    Button
  },
  data: () => {
    return {
      message: ""
    }
  },
  methods: {
    emitTranslate: function() {
      this.$emit('translate', this.message)
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

input {
  height: 100%;
  font-size: 30px;
}

input {
  margin-right: 10px;
  width: 200px;
  background-color: transparent;
  border: none;
  border-bottom: 1px solid grey;
}
</style>
