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
import footerbar from "@/components/footerbar";
import principalHome from "@/components/principalHome";
import allUsers from "@/components/allUsers";

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