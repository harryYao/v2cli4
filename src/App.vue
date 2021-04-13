<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <fieldset>
      <legend>template中使用环境变量</legend>
      <div>API: {{ api }}</div>
    </fieldset>
    <show-img></show-img>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ShowImg from './components/ShowImg.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    ShowImg
  },
  data() {
    return {
      api: process.env.VUE_APP_API
    }
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
