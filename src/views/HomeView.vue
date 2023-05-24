<template>
  <div class="home">
    <div class="wrapper">  
      <h1>¡DESCUBRE PHONE FINDER!</h1>
         <video width="640" height="360" controls>
           <source src="../assets/PHONE_FINDER_INTRO_ESPAÑOL.mp4" type="video/mp4">
           Tu navegador no admite el elemento de video.
        </video>
    <h1>¡MIRA EL VIDEO AQUÍ!</h1>
    <h1>¡INSTRUCCIONES PARA USAR PHONE FINDER!</h1>
         <video width="640" height="360" controls>
           <source src="../assets/instruccionesPHONEFINDER.mp4" type="video/mp4">
           Tu navegador no admite el elemento de video.
        </video>
    <h1>¡MIRA EL VIDEO AQUÍ!</h1>
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
      await fetch('http://localhost:3000', {
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
  display: flex;
  justify-content: flex-start;
  align-items: center;
  flex-direction: column;
  min-height: min-content;
  padding: 5px 0;
  min-width: 100vw;
  height: min-content;
 overflow: hidden;
 animation: background 10s infinite;
 padding: 5%;
 text-align: center;
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
source{
  margin: 5%;
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
h1{
 font-size: 6vh;
 text-align: center;
}
@media (max-width: 1200px) {
  .wrapper{
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  grid-auto-rows:min-content,min-content;
  animation: background 10s infinite;
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
 color: #f00;
  }25%{
    background-color: #f00;
    color: #000;
  }
  50%{
 background-color: #000;
 color: #f00;
  }75%{
    background-color: #f00;
    color: #000;
  }100%{
 background-color: #000;
 color: #f00;
  }
}
</style>