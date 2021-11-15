<template>
  <ComponentX componentValue="X"/>
  <ComponentY componentValue="Y"/>
  <img alt="Vue logo" src="./assets/logo.png">
  <!--  <HelloWorld msg="Welcome to Your Vue.js App"/>-->
  <HelloWorld :msg="message"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ComponentX from "./components/ComponentX";
import ComponentY from "./components/ComponentY";

export default {
  name: 'App',
  components: {
    ComponentY,
    ComponentX,
    HelloWorld
  },
  data() {
    return {
      message: '"Hello World" message from App data() using props'
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

h1, h2, h3 {
  color: #42b983;
}
</style>
