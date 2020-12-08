<template>
  <div class="purchase">
    <div class="purchase-text">
      <h1 class="text-anytime">
        <strong>Purchase Anytime</strong>
      </h1><br>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>

    </div>
    <div>
      <img class="phone" src="../assets/phone.png">
    </div>
  </div>
</template>

<script>
export default {
  name: "purchase"
}
</script>

<style scoped>
.purchase{
  background-image: url("../assets/visa-transparent.png");
  background-size: 50%;
}
p{
  width: 80%;
  display: inline-block;
  color: black;
}

.phone{
  width: 30%;
}

.purchase-text{
  float: left;
}

.purchase{
  margin-top: 50px;
}
</style>