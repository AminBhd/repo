<template>
  <div id="app">
    <HomeApp/>
  </div>
</template>

<script>
import HomeApp from './components/Home.vue'

export default {
  name: 'App',
  components: {
    HomeApp
  }
}
</script>

<style>
body{
  overflow: hidden;
  margin: 0px;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
