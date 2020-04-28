<template>
  <div>
    <p>Clicked {{ count }} times! Count is {{ parity }}.</p>
    <button @click="increment" variant="success">Increment</button>
    <button @click="decrement" variant="danger">Decrement</button>
    <button @click="incrementIfOdd" variant="info">Increment if Odd</button>
    <button @click="incrementAsync" variant="warning">Increment Async</button>
  </div>
</template>

<script>
export default {
  name: 'Counter',
  data: function() {
    return {
      count: 0
    };
  },
  computed: {
    parity: function() {
      return this.count % 2 === 0 ? 'even' : 'odd';
    }
  },
  methods: {
    increment: function () {
      this.count++;
    },
    decrement: function () {
      this.count--;
    },
    incrementIfOdd: function () {
      if (this.parity === 'odd') {
        this.increment();
      }
    },
    incrementAsync: function () {
      setTimeout(() => {
        this.increment()
      }, 1000)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
