<template>
  <div>
    <div class="logo">
      <h1>Todo List</h1>
    </div>
    <div id="nav">
      <router-link to="/">Home</router-link>
      ||
      <router-link to="/about">About</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style scoped>
  div.logo {
    padding: 2% 5%;
    background-color: #2c3e50;
    color: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  div#nav {
    border-bottom: 1px solid #2c3e50;
    display: flex;
    justify-content: center;
  }

</style>