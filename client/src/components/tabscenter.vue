<template>
  <div class="tabs">
    <div>
      <a class="button2">
        <img class="check" src="../assets/check.png">
        <p>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo.</p>
      </a>
      <a class="button2">
        <img class="check" src="../assets/check.png">
        <p>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo.</p>
      </a>
      <a class="button2">
        <img class="check" src="../assets/check.png">
        <p>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo.</p>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "tabscenter"
}
</script>

<style scoped>
p{
  width: 200px;
}
.check{
  width: 40px;
}

a.button2{
  display:inline-block;
  padding:0.5em 3em;
  border:0.16em solid gray;
  margin:0 0.3em 0.3em 0;
  box-sizing: border-box;
  border-radius: 25px;
  text-decoration:none;
  font-family:'Roboto',sans-serif;
  font-weight:400;
  color:black;
  text-align:center;
  transition: all 0.15s;
}
a.button2:hover{
  color:#DDDDDD;
  border-color:#DDDDDD;
}
a.button2:active{
  color:#BBBBBB;
  border-color:#BBBBBB;
}
@media all and (max-width:30em){
  a.button2{
    display:block;
    margin:0.4em auto;
    }
}
</style>