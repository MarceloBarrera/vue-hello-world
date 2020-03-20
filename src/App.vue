<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <p v-once> {{title}} </p>
    <p> {{sayHello()}} </p>
    <a v-bind:href="link">Google</a>
    <hr>
    <p>
      {{finishedLink}}      
    </p>
    <p v-html="finishedLink">       
    </p>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
   data() {
    return {
      title: 'Hello pepepeppepe!!!!!!!!!!!!!!!!!!',
      link: 'http://google.com',
      finishedLink: '<a href="http://google.com"> Google <a/>'
      }
  },
  methods: {
    sayHello() {
      this.title = 'HELLO!'
      return 'MAMAMAMAMAAM' + this.title;
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
