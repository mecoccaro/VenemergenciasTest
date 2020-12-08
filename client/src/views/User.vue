<template>
  <div>
    <div class="top">
      <navbar/>
      <img id="userM" src="../assets/user-male.png">
      <h1 style="padding-bottom: 20px; color: white;">
        User information
      </h1>
    </div>
    <div>
      <singleUser/>
    </div>

    <footerbar/>
  </div>
</template>

<script>
import navbar from "@/components/navbar";
import footerbar from "@/components/footerbar";
import singleUser from "@/components/singleUser";

export default {
  name: "User",
  components:
  {
    navbar,
    footerbar,
    singleUser
  }
}
</script>

<style scoped>

</style>