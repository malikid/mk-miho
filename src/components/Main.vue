<template>
  <div class="main" v-bind:class="{ stickToTop }">
    <Logo :stickToTop="stickToTop" />
    <div class="panel">
      <div class="areas">
        <div>臺灣</div>
        <div>to</div>
        <div>大陸</div>
      </div>
      <SearchBar
        :stickToTop="stickToTop"
        v-on:translate="$emit('translate', $event)"
      />
    </div>
  </div>
</template>

<script>
import Logo from './Logo.vue'
import SearchBar from './SearchBar.vue'

export default {
  name: 'Main',
  props: {
    stickToTop: Boolean
  },
  components: {
    Logo,
    SearchBar
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.main {
  position: fixed;
  top: 0;
  left: 0;
  flex: 1;
  height: 100%;
  width: 100%;
  background-color: #FFE75B;
  border: 0.5px grey solid;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  transition: height 0.5s, flex-direction 0.5s, justify-content 0.5s;
}

.stickToTop {
  height: 100px;
  justify-content: initial;
}

.panel {
  margin-left: 80px;
  height: 200px;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: start;
}

.stickToTop .panel {
  margin-left: 50px;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.areas {
  width: 250px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  font-size: 40px;
}

.stickToTop .areas {
  width: auto;
  height: 70px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-size: inherit;
}
</style>
