<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" style="width: 200px; margin: auto;">
    <LayoutChange/>
  </div>
</template>

<script>
import LayoutChange from './components/LayoutChange.vue'

export default {
  name: 'App',
  components: {
    LayoutChange
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
</style>
