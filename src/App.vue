<template>
  <div id="app">
    <button @click="decrement">-</button>
    {{$store.state.count}}
    {{evenOrOdd}}
    <button @click="increment">+</button>
    <button @click="incrementIfOdd">Increment if odd</button>
    <button @click="incrementAsync">Increment async</button>
  </div>
</template>

<script>
// 借
import { mapActions, mapGetters } from 'vuex'
export default {
  name: 'App',
  components: {
   
  },
  methods: mapActions([
    'increment',
    'decrement',
    'incrementIfOdd',
    'incrementAsync'
  ]),
  computed: 
    // 如果有多处要用到奇偶判断怎么办？
    // evenOrOdd() {
    //   return this.$store.state.count % 2 === 0 ? 'even' : 'odd' 
    // }
    mapGetters([
      'evenOrOdd'
    ])
  
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
