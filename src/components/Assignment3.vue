<template>
  <div id='exercise'>
    <!-- 1) Show a 'result' of 'not there yet' as long as 'value' is not equal to 37 - you can change 'value' with the buttons. Print 'done' once you did it -->
    <div>
      <p>Current Value: {{ result }}</p>
      <button @click="add(5)">Add 5</button>
      <button @click="add(1)">Add 1</button>
      <p>{{ result == 37 ? 'Done!' : 'Not there yet.' }}</p>
    </div>
    <!-- 2) Watch for changes in the 'result' and reset the 'value' after 5 seconds (hint: setTimeout(..., 5000) -->
  </div>
</template>

<script>
export default {
  name: 'Assignment3',
  data () {
    return {
      result: 0
    }
  },
  methods: {
    add: function (step) {
      this.result += step
    }
  },
  watch: {
    result: function () {
      if (this.result >= 37) {
        setTimeout(() => {
          this.result = 0
        }, 5000)
      }
    }
  }
}
</script>

<!-- Add 'scoped' attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
