<template>
  <div id="app">
    <img src="./assets/logo.png">
    <HelloWorld />
    <comp-header />
    <list-products />
    <comp-footer />
  </div>
</template>

<script>
/*
App
  Header
  ListProducts
    Product
    Product
    Product
  Footer
*/

import HelloWorld from './components/HelloWorld'
import CompHeader from './components/CompHeader'
import CompFooter from './components/CompFooter'
import ListProducts from './components/ListProducts'

export default {
  name: 'App',
  components: {
    HelloWorld,
    CompHeader,
    ListProducts,
    CompFooter
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
