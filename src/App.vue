<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link :to="{name: 'SearchView'}">Search</router-link> |
    <router-link :to="{name:'TestView'}">Test</router-link>
  </nav>
  <router-view/>
</template>

<style global>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body{
  margin: 0;
  background-color: lightcyan;
}
nav {
  padding: 20px;
  
}

nav a {
  margin: 5px;
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
}

nav a.router-link-exact-active {
  color: white;
  background-color: darkgray;
  padding: 5px;
  border-radius: 5px;
}
</style>
