<template>
  <div id="app">
    <img src="./assets/logo.png">
    <HelloWorld />
    <comp-header 
      :title="title"/>
    <list-products />
    <list-user 
      v-bind:listUser='listUser'/>
    <comp-footer 
      />
  </div>
</template>

<script>
/*
App (title, listUser[])
  Header (title)
  ListUser (listUser[])
    User (user - object)
    User (user - object)
    User (user - object)
  Footer (title)
*/

import HelloWorld from './components/HelloWorld'
import CompHeader from './components/CompHeader'
import CompFooter from './components/CompFooter'
import ListProducts from './components/ListProducts'
import ListUser from './components/ListUser'

export default {
  name: 'App',
  data() {
    return {
      title: 'Hello VueJS - Header ..',
      listUser: [
        {id: 1, email: 'email1@gmail.com', active: true},
        {id: 101, email: 'email2@gmail.com', active: false},
        {id: 123, email: 'email3@gmail.com', active: true}
      ]
    }
  },
  components: {
    HelloWorld,
    CompHeader,
    ListProducts,
    ListUser,
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
