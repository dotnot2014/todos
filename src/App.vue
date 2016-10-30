<template>
  <div id="app">
    <list></list>
  </div>
</template>

<script>
import List from './components/list'

export default {
  name: 'app',
  components: {
    List
  }
}
</script>

<style>
#app {
  font-family: '微软雅黑', Helvetica, Arial, sans-serif;
  margin-left:200px;
  width:500px;
  color: #2c3e50;
}
</style>
