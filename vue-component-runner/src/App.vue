<template>
  <div id="app">
   <NavBar></NavBar>
  </div>
</template>

<script>
import NavBar from './components/navbar/NavBar'
export default {
  name: 'App',
  components: {
    NavBar
  }
}
</script>

<style >
@import './assets/iconfont/iconfont.css';
* {
  margin: 0;
  padding: 0;
}
</style>
