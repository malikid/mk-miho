<template>
  <div id="answer" v-html="answer">
  </div>
</template>

<script>
import db from '../db.js'

export default {
  name: 'Answer',
  props: {
    input: String
  },
  computed: {
    answer: function () {
      const input = this.input
      return input ? (
        db[input] ? "<span>" + db[input] + "</span>&nbsp;&nbsp;&nbsp;<<&nbsp;就是這個！！！" :
        "找不到欸... 再試試別的!?"
      ) : ""
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
#answer {
  margin: 30px 0 0;
  font-size: 20px;
}

#answer span {
  font-size: 30px;
  font-weight: bold;
}

@media only screen and (max-width: 768px) {
  #answer {
    margin: 30px 0 0;
    font-size: 15px;
  }

  #answer span {
    font-size: 20px;
    font-weight: bold;
  }
}
</style>
