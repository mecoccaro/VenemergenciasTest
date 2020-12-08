<template>
  <div class="topnav">
    <img id="logo-nav" src="../assets/visa-logo.png" align="left">
    <div class="botones-nav">
      <router-link class="active" to="/principal"><strong>Vista principal</strong></router-link>
      <a href="#news">News</a>
      <a href="#contact">Contact</a>
      <a href="#about">About</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "navbar"
}
</script>

<style scoped>
.topnav {
  overflow: hidden;
  background: linear-gradient(90deg, rgba(150,118,238,1) 0%, rgba(122,56,200,1) 35%, rgba(140,7,246,1) 100%);
  padding-bottom: 50px;
}

.topnav a {
  float: left;
  color: #f2f2f2;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
}

.topnav a:hover {
  background-color: #875fc4;
  color: black;
}

.topnav a.active {
  background-color: #340a60;
  color: white;
}

#logo-nav {
  width: 100px;
  justify-content: center;
}

.botones-nav{
  float: right;
}

a.boton1{
  display:inline-block;
  text-decoration:none;
  font-weight:300;
  color:#FFFFFF;
  text-align:center;
}
a.boton1:hover{
  color:#000000;
}
@media all and (max-width:30em){
  a.boton1{
    display:block;
    }
}


</style>