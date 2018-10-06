<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  //color: #2c3e50;
  color: orange;
}

#app button{
  text-decoration: underline;
}

#nav {
  padding: 30px;
  a {
    font-weight: bold;
    //color: #2c3e50;
    color: orange;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
@import "~vue-material/dist/theme/engine"; // Import the theme engine

@include md-register-theme("default", (
  primary: md-get-palette-color(orange, A200), // The primary color of your application
  accent: md-get-palette-color(yellow, A200), // The accent or secondary color
  theme: dark // This can be dark or light
));

@import "~vue-material/dist/theme/all"; // Apply the theme

</style>
