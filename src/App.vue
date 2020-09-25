<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to NoteVue.js"/>
  <Credits/>  

</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Credits from './components/Credits.vue'


export default {
  name: 'App',
  components: {
    HelloWorld, Credits
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
  margin-top: 100px;
  
}
body{
  background-color: #74a377;
}

</style>