<template>
  <div id="app">
    <List />
  </div>
</template>

<script>
import List from './components/List.vue'

export default {
  name: 'App',
  components: {
    List
  }
}
</script>

<style>
#app {
  margin-top: 50px;
  text-align: center;
}
</style>
