<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> ||
      <router-link to="/search">Search</router-link>
    </div>
    <Header />
    <router-view />
  </div>
</template>
<script>
import Header from "./components/Header";
export default {
  name: "App",
  components: {
    Header,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}

#nav {
  background: rgba(44, 62, 80, 0.5);
  padding: 15px;
}

#nav a {
  font-weight: bold;
  color: #fff;
  text-decoration: none;
}

#nav a.router-link-exact-active {
  color: crimson;
}
</style>
