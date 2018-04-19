<template>
  <div id="optionsContainer">
    <div
      class="option"
      v-bind:key="'from-' + fromOptionKey"
      v-for="fromOptionKey in fromToOptionsKeys"
    >
      <div
        v-bind:key="'to-' + toOptionKey"
        v-for="toOptionKey in fromToOptionsKeys"
        v-if="fromOptionKey != toOptionKey"
        v-on:click="$emit('setFromTo', {from: fromOptionKey, to: toOptionKey})"
      >
        從
        <span>{{fromToOptions[fromOptionKey]}}</span>
        詞彙找
        <span>{{fromToOptions[toOptionKey]}}</span>
        用語
      </div>
    </div>
  </div>
</template>

<script>
import {fromToOptions} from "../config.js"

export default {
  name: 'Options',
  data: () => ({
    fromToOptions,
    fromToOptionsKeys: Object.keys(fromToOptions)
  })
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#optionsContainer {
  display: flex;
  flex-direction: column;
}

.option {
  flex: 1;
  margin: 5px;
  padding: 10px;
  border: 1px grey solid;
  background-color: white;
  font-size: 30px;
  opacity: 0.8;
  cursor: pointer;
}

.option:hover {
  opacity: 0.6;
}
</style>
