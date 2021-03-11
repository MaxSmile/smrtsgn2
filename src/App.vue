<template>
  <div id="app">
    
    <WebViewer initialDoc="https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"/>
  </div>
</template>
 
<script>
import WebViewer from './components/WebViewer.vue'

export default {
  name: 'App',
  components: {
    WebViewer
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
