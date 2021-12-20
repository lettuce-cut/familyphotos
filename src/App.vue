<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/browse">Browse</router-link> | 
      <router-link to='/view'>View Photos</router-link> | 
      <router-link class='people' to='#' v-if="cartSize==1">{{cartSize}} person chosen</router-link>
      <router-link class='people' to='#' v-if="cartSize!=1">{{cartSize}} people chosen</router-link>
    </div>
    <router-view/>
    <footer>
      <hr>
      <p><a class='git' href="https://github.com/lettuce-cut/familyphotos.git">GITHUB REPO</a></p>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  computed: {
    cartSize() {
      return this.$root.$data.cart.length
    }
  },
}
</script>

<style>

footer {
  padding-block: 25px 0px;
  position:relative;
  bottom:0;
  width:100%;
  height:60px;   /* Height of the footer */
}
.people {
  text-decoration: none;
}
.git {
  text-decoration: none;
  color:black;
}

.git:hover {
  color: goldenrod;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: black;
}
hr{
  border: 1px black solid;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: black;
}

#nav a.router-link-exact-active {
  color: goldenrod;
}
</style>
