<template>
  <div class="principal">
    <img id="userM" src="../assets/user-male.png">
    <h1 style="padding-bottom: 20px">
      Vista Principal
    </h1>
  </div>
</template>

<script>
export default {
  name: "principalHome"
}
</script>

<style scoped>
.principal{
  margin: 0;
}
h1, p{
  color: white;
  font-family:'Roboto',sans-serif;
}
#userM{
  width: 20%;
}
</style>