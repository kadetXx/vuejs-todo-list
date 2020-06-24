<template>
  <div id="app">
    <Header />
    <router-view/>
  </div>
</template>

<script>

import Header from './components/header'

export default {
  name: 'App',
  components: {
    Header
  }
}
</script>

<style>
  #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  }

  #nav {
    padding: 15px;
    text-align: center;
  }

  #nav a {
    font-weight: bold;
    color: #2c3e50;
    margin: 0 10px;
    text-decoration: none;
  }

  #nav a.router-link-exact-active {
    color: #42b983;
  }
</style>
