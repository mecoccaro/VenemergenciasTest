<template>
  <div>
    <div class="top">
      <navbar/>
      <principalHome/>
    </div>
    <div>
      <allUsers/>
    </div>
    <div>
      <footerbar/>
    </div>

  </div>

</template>

<script>
import navbar from "@/components/navbar";
import principalHome from "@/components/principalHome";
import allUsers from "@/components/allUsers";
import footerbar from "@/components/footerbar";

export default {
  name: "Principal",
  components:
      {
        navbar,
        principalHome,
        allUsers,
        footerbar
      },
}
</script>

<style scoped>

</style>