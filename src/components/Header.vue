<template>
  <div id="header">
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
    <router-link to="/concerts">Concerts</router-link>
    <router-link to="/concours">Concours</router-link>
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style scoped>
#header {
  background-color: bisque;
}
</style>
