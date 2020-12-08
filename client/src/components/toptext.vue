<template>
  <div class="tope" >
    <h1 align="center" class="text">Be Smart Take Card</h1>
    <p align="center" class="text">The acquisition supports Visa's network of networks strategy and goal of being a single point</p>
    <p align="center" class="text"> of connection for the movement of money for all.</p>
    <a class="boton1">Read more</a>
  </div>
</template>

<script>
export default {
  name: "toptext"
}
</script>

<style scoped>
.tope{
  display: inline;
  text-align: justify;
  text-justify: inter-word;
}
.text{
  color: white;
}

a.boton1{
  display:inline-block;
  padding:0.35em 1.2em;
  border:0.1em solid #FFFFFF;
  margin:0 0.3em 0.3em 0;
  border-radius:0.12em;
  box-sizing: border-box;
  text-decoration:none;
  font-family:'Roboto',sans-serif;
  font-weight:300;
  color:#FFFFFF;
  text-align:center;
  transition: all 0.2s;
}

a.boton1:hover{
  background-color: #340a60;
  border-color: #340a60;
}
@media all and (max-width:30em){
  a.boton1{
    display:block;
    margin:0.4em auto;
  }
}
</style>