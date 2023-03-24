<template>
  <div class="tutorialDiv">
    <h1 class="title"> COMO USAR PHONEFINDER </h1>
    <h1 class="title2"> 1- Descarga telegram</h1>
    <img class="telegramPic" src="../assets/telegram.png" alt="">
    <p>Soy un bot de telegram, por lo tanto, si no tienes instalado telegram, es imposible para mi comunicarme contigo.</p>
    <h1 class="title2"> 2- Buscame y hablame</h1>
    <img class="instructions" src="../assets/instrucciones.png" alt="">
    <p>Mi nombre de usuario en telegram es "@phoneFinderChileBot". ahora, solo te hace falta escribirme el mensaje que tu quieras para poder agregarte a mi base de datos.</p>
  </div>
</template>
<script>
</script>
<style scoped>
.tutorialDiv{
display:flex;
max-width:100vw;
flex-direction: column;
width:100vw;
height:min-content;
background-color:#000;
align-items: center;
}
.telegramPic{
  max-height: 50vh;
  max-width: 50vh;
}
.instructions{
width:1280px;
height:720px ;
}
.title{
color:#f00;
text-align: center;
font-family: 'Roboto Mono', monospace;
font-size: 5vh;
}
.title2{
color:#fff;
text-align: center;
}
h1,img{
padding:2vh;
}
p{
  color: #f00;
  font-size: x-large;
  text-align: center;
}
@media (max-width: 1200px) {
  .instructions{
width:854px;
height:480px;
}
}
@media (max-width: 800px) {
  .instructions{
width:640px;
height:360px;
}
}
@media (max-width: 600px) {
  .instructions{
width:480px;
height:270px;
}
}
</style>