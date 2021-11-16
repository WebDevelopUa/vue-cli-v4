<template>
  <ComponentX :RootComponentPropsName="name"
              :RootComponentPropsAge="age"
              @age-reduce="age--"
              @age-reset="resetAge"
              :resetAgeCallbackFn="resetAgeCallback"
  />
  <ComponentY :RootComponentPropsAge="age"/>

  <!-- Button #1 -->
  <button type="button"
          @click="age++">
    RootComponentPropsAge++
  </button>

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
      message: '"Hello World" message from App data() using props',
      name: 'Tom',
      age: 20
    }
  },
  methods:
      {
        resetAge(num) {
          this.age = num
        },
        resetAgeCallback(num){
          this.age = num
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
