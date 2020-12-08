<template>
  <div class="principal">
    <div class="top">
      <navbar></navbar>
      <toptext></toptext>
    </div>
    <div class="tarjeta">
      <img src="../assets/credit_card_PNG37.png" id="tdc">
    </div>
    <div class="mid">
      <card></card>
    </div>
    <div style="margin-top: 20px">
      <tabscenter></tabscenter>
    </div>
    <div>
      <purchase></purchase>
    </div>
    <div style="margin-top: 30px; padding-bottom: 100px">
      <carousel></carousel>
    </div>
    <div>
      <footerbar/>
    </div>
  </div>

</template>

<script>
import navbar from "@/components/navbar";
import toptext from "@/components/toptext";
import card from "@/components/card";
import tabscenter from "@/components/tabscenter";
import carousel from "@/components/carousel";
import purchase from "@/components/purchase";
import footerbar from "@/components/footerbar";

export default {
  name: 'Home',
  components: {
    navbar,
    toptext,
    card,
    tabscenter,
    carousel,
    purchase,
    footerbar
  }
}
</script>
<style>
body{
  margin: 0px;
}
.top{
  border-top-color: rgb(150,118,238);
  background: rgb(150,118,238);
  background: linear-gradient(90deg, rgba(150,118,238,1) 0%, rgba(122,56,200,1) 35%, rgba(140,7,246,1) 100%);
  border-radius: 0 0 35% 35%;


}

#tdc{
  width: 50%;
  justify-content: center;
}
</style>
