<template>
  <div id="app">
    <MorphBtn/>
  </div>
</template>

<script>
import MorphBtn from './components/MorphBtn.vue'

export default {
  name: 'app',
  components: {
    MorphBtn
  }
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
