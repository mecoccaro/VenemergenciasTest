<template>
  <div class="navbar">
    <nav>
      <div>
        <img id="logo-nav" src="../assets/visa-logo.png" align="left">
      </div>
      <div>
        <router-link class="boton1" to="/principal"><strong>Vista principal</strong></router-link>
      </div>
      <div align="right">
        <a id="support" class="texts">Support</a>
      </div>

    </nav>
  </div>
</template>

<script>
export default {
  name: "navbar"
}
</script>

<style scoped>

#logo-nav {
  width: 100px;
  justify-content: center;
}
.navbar{
  margin-bottom: 10%;
}
.texts {
  font-family: Tahoma;
  color: white;
  margin: auto;
  width: 50%;
  padding: 10px;
}
#support{
  margin-right: 50px;
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