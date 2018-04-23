<template>
  <div class="main">
    <Logo class="layout" />
    <div :class="{layout: true, panel: true, changing}">
      <Question :step="step" />
      <Options
        v-if="step === STEP_SET_FROM_TO"
        v-on:setFromTo="setFromTo"
      />
      <Input
        v-else-if="step === STEP_TRANSLATE"
        v-on:translate="translate"
      />
      <Answer :input="input" />
    </div>
  </div>
</template>

<script>
import Logo from './Logo.vue'
import Question from './Question.vue'
import Options from './Options.vue'
import Input from './Input.vue'
import Answer from './Answer.vue'

import {STEP_SET_FROM_TO, STEP_TRANSLATE} from '../constants.js'

export default {
  name: 'Main',
  components: {
    Logo,
    Question,
    Options,
    Input,
    Answer
  },
  data: () => {
    return {
      STEP_SET_FROM_TO,
      STEP_TRANSLATE,
      step: STEP_SET_FROM_TO,
      from: "",
      to: "",
      changingStep: false,
      input: "",
    }
  },
  computed: {
    changing: function () {
      return this.changingStep
    }
  },
  methods: {
    setFromTo: function ({from, to}) {
      this.from = from
      this.to = to
      this.changingStep = true
      setTimeout(() => {
        this.step = STEP_TRANSLATE
        this.changingStep = false
      }, 200)
    },
    translate: function (msg) {
      this.input = msg
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.main {
  width: 100%;
  height: 100%;
  background-color: #FFE75B;
  background-image: radial-gradient(circle at 55% 50%, yellow 30%, orange);
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.layout {
  margin-bottom: 5%;
}

.panel {
  margin-left: 100px;
  width: 450px;
  height: 220px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
  opacity: 0.7;
  transition: opacity 0.2s;
}

.changing {
  opacity: 0;
}

@media only screen and (max-width: 768px) {
  .main {
    width: 100%;
    height: 100%;
    background-color: #FFE75B;
    background-image: radial-gradient(circle at 50% 60%, yellow 30%, orange);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .panel {
    margin-left: 0;
    width: 270px;
    height: auto;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    opacity: 0.7;
    transition: opacity 0.2s;
  }
}
</style>
