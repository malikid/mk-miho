<template>
  <div id="question">
    {{question}}
  </div>
</template>

<script>
import {QUESTIONS} from '../constants.js'

export default {
  name: 'Question',
  props: {
    step: Number
  },
  data: () => {
    return {
      QUESTIONS
    }
  },
  computed: {
    question: function () {
      return this.QUESTIONS[this.step]
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#question {
  margin: 30px 0;
  font-size: 25px;
}

@media only screen and (max-width: 768px) {
  #question {
    margin: 30px 0;
    font-size: 18px;
  }
}
</style>
