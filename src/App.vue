<template>

  <!--  #1 pass down the sections to the form inside AppForm component; render with a <slot> tag -->
  <AppForm>
    <div class="help">
      <p><i>Form status info</i></p>
    </div>
    <div class="fields">
      <input type="text" placeholder="email">
      <input type="text" placeholder="username">
      <input type="password" placeholder="password">
    </div>
    <div class="buttons">
      <button type="submit">
        Send
      </button>
    </div>
  </AppForm>

  <!-- #2 -->
  <AppForm/>

  <br/>
  <hr/>
  <br/>

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
import AppForm from "./components/AppForm";

export default {
  name: 'App',
  components: {
    AppForm,
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
        resetAgeCallback(num) {
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
