<template>
  <div class="carousel">
    <h1 id="choose">Choose Your Card</h1>
    <p>Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid ex ea commodi consequatur? Quis autem vel eum iure reprehenderit qui in ea voluptate velit esse quam nihil molestiae consequatur, vel illum qui dolorem eum fugiat quo voluptas nulla pariatur?</p>
    <div class="tarjetas">
      <img class="tdc-varias" src="../assets/credit_card_PNG207.png">
      <img class="tdc-varias" src="../assets/credit_card_PNG78.png">
      <img class="tdc-varias" src="../assets/credit_card_PNG207.png">
    </div>
  </div>
</template>

<script>
export default {
name: "carousel"
}
</script>

<style scoped>
p{
  width: 80%;
  display: inline-block;
  color: #BBBBBB;
}
#choose{
  color: black;
  font-family: Tahoma;
  padding-top: 30px;
}
.tdc-varias{
  width: 30%;
}
.carousel{
  background:
      linear-gradient(to bottom right, #875fc4 50%, transparent 50.5%) no-repeat bottom,
      linear-gradient(0deg, #875fc4, #875fc4) no-repeat top;
  color: white;
  padding-bottom: 3em;
  background-size: 100% 7em, 100% calc(100% - 7em)
}

</style>