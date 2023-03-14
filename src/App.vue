<template>
  <nav>
    <div class="logoDiv">
      <img src="./assets/phoneFinderLogo.png" alt="">
    </div>

    <div class="options">
      <router-link to="/">Menú principal</router-link> 
      <router-link to="/about">Tutorial</router-link>
    </div>

  </nav>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
*{
  padding: auto;
  margin: auto;
}
nav {
  padding: 0;
  background-color: #42b983;
  min-width: 100vw;
  height:min-content;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.options{
background-color: aqua;
}
.logoDiv{
  min-height: min-content;
  background-color: black;
}
nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
