<template>
  <div>
    <div class="logo">
      <h1>TodoList</h1>
    </div>
    <div id="nav">
      <router-link to="/">Home</router-link>
      <span class="menu-divide">||</span>
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
    background-color: #2e7c59;
    color: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  h1 {
    font-size: 23px;
  }

  div#nav {
    border-bottom: 1px solid #2e7c59;
    display: flex;
    justify-content: center;
  }

  .menu-divide {
    color: grey;
  }

</style>