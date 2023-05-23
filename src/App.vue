<template>
  <nav>
    <div class="logoDiv">
      <img src="./assets/phoneFinderLogo.png" alt="">
    </div>

    <div class="options">
      <router-link class="routerLink" style="font-size: x-large;" to="/">Menú principal</router-link> 
      <router-link class="routerLink" style="font-size: x-large;" to="/about">buscar telefono</router-link>
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
  max-width:100vw;
  overflow: hidden;
}
*{
 box-sizing: border-box;
 margin: 0;padding: 0;
}
nav {
  padding: 0;
  background-color: #000;
  width: 100vw;
  max-width: 100vw;
  height:min-content;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.options {
  max-width: 50vw; /* ajustar según sea necesario */
  margin-top: 3vh;
  margin-bottom: 3vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.routerLink{
margin: 3vh;
font-size: xx-large;
}
.logoDiv{
  min-height: min-content;
  min-width: 100vw;
  max-width: 100vw;
  background-color:#000;
  overflow: hidden;
  display: flex;
  justify-content: center;
}
.logoDiv img{
height: 25vh;
padding: 0;

}
nav a {
  font-weight: bold;
  color: #f00;
}
nav a.router-link-exact-active {
  color: #ffff;
}
@media (max-width: 1200px) {
  .logoDiv img{
    height: 15vh;
  }

}
</style>