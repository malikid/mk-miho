<template>
  <div id="optionsContainer">
    <div class="options">
      從
      <select autofocus v-model="from" @keyup.enter="emitSetFromTo">
        <option
          v-for="fromOptionKey in fromOptionsKeys"
          v-bind:key="'from-' + fromOptionKey"
          :selected="fromOptionKey == defaultFrom"
          :value="fromOptionKey"
        >
          {{fromToOptions[fromOptionKey]}}
        </option>
      </select>
      詞彙找
      <select v-model="to" @keyup.enter="emitSetFromTo">
        <option
          v-for="toOptionKey in toOptionsKeys"
          v-bind:key="'to-' + toOptionKey"
          :disabled="toOptionKey === from"
          :value="toOptionKey"
          :selected="toOptionKey == defaultTo"
        >
          {{fromToOptions[toOptionKey]}}
        </option>
      </select>
      用語
    </div>
    <Button text="ENTER" :handler="emitSetFromTo" />
  </div>
</template>

<script>
import {fromToOptions} from "../config.js"
import Button from "./Button.vue"

export default {
  name: 'Options',
  components: {
    Button
  },
  data: () => ({
    fromToOptions,
    defaultFrom: "taiwan",
    from: "taiwan",
    defaultTo: "china",
    to: "china",
  }),
  computed: {
    fromOptionsKeys: function() {
      return Object.keys(fromToOptions)
    },
    toOptionsKeys: function() {
      const filteredKeys = this.fromOptionsKeys.filter(key => (key != this.from))
      this.to = filteredKeys[0];
      return filteredKeys
    }
  },
  methods: {
    emitSetFromTo: function() {
      this.$emit('setFromTo', {from: this.from, to: this.to})
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.options {
  font-size: 30px;
  margin-bottom: 30px;
}

select {
  border: 1px black solid;
  background-color: transparent;
  font-size: 30px;
  cursor: pointer;
}

select:hover {
  border-width: 2px;
}

@media only screen and (max-width: 768px) {
  .options {
    font-size: 20px;
    margin-bottom: 30px;
  }

  select {
    border: 1px black solid;
    background-color: transparent;
    font-size: 20px;
    cursor: pointer;
  }
}
</style>
