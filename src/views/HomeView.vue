<template>
  <div class="home">
    <div class="wrapper">  
       <div class="instructions">
        <img src="../assets/phoneFinderBot.png" alt="">
        <h1 class="title firstTitle">hola, soy phoneFinder y haré vibrar o sonar tu telefono siempre que lo pierdas. siempre estaré aquí para ti si eso pasa. si no me conoces aún, puedes seguir las instrucciones para aprender a usarme</h1>
       </div>
       <div class="userInput">
         <h1 class="title">Escribe tu nombre de usuario en telegram sin el "@"</h1>
         <input id='username' v-model="username" type="text">
         <input type="button" v-if="send" class="button" value="buscar telefono" v-on:click="findPhone()"> 
         <input type="button" v-if="!send" class="button" value="buscando..."> 
       </div> 
    </div> 
  </div>
</template>
<script>
import axios from 'axios'
export default 
{
  name: 'HomeView',
  components: {},
  data() {
    return {
      username: "",
      send:true
    }
  },
  methods: {
    
   async findPhone() 
    {
      console.log(this.username)
      await fetch('https://phonefinderbotserver-production.up.railway.app/findPhone', {
      method: 'POST',
      headers: {
       'Content-Type': 'application/json'
      },
      body: JSON.stringify({ username: this.username })
     })
     .then(response => response.json())
     .then(data => {
      console.log(data);
     })
     .catch(error => {
     console.error(error);
     });
    this.send=false
    setTimeout(()=>{
      this.send=true
     },10000)
    }
  }
}
</script>
<style scoped>
*{
  box-sizing: border-box;
  margin: 0;
padding: 0;
}
.home{
display:flex;
justify-content:center;
align-content:center;
align-items:center;
min-width:100vw;
min-height:min-content;
overflow: hidden;
animation-name: background;
animation-duration: 2s;
animation-fill-mode: forwards;
animation-iteration-count: infinite;

}

.wrapper{
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 5px; /*The space between grid containers*/
  min-height: min-content;
  padding: 5px 0;
  min-width: 100vw;
  height: 100vh;
 overflow: hidden;
}
.userInput,.instructions{
min-height:min-content;
min-width:100%;
display:flex;
flex-direction: column;
justify-content:center;
align-items:center;
padding: 5vh;
overflow: hidden;
}
#username{
  width: 30vw;
  margin: 3vh;
  height: 5vh;
  font-size: x-large;
  text-align: center;
}
.userInput{
  background-color:#000;
}
.instructions{
  background-color:#000;

}
.button{
  border:3px solid #f00;
  background: none;
  color: #fff;
  height: 7vh;
  font-weight:900;
  font-size: x-large;
  cursor: pointer;
}
.button:hover{
  background: #900;
}
.title{
color: #f00;
text-align: center;
}
@media (max-width: 1200px) {
  .wrapper{
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  grid-auto-rows:min-content,min-content;
  animation: background 3s infinite;
  max-width: 100vw;

}
#username{
  width: 60vw;
  margin: 3vh;
  height: 5vh;
  font-size: x-large;
  text-align: center;
}
img{
  height: 40vh;
  margin: 2vh;
border:2px solid #f00;
}
@media (max-width: 800px) {

img{
  height: 20vh;
}
.firstTitle{
  font-size: large;
}
}
}
@keyframes background{
  0%{
 background-color: #000;
  }100%{
    background-color: #f00;
  }
}
</style>