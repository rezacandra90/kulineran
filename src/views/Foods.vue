<template>
  <div>
    <Navbar />
    <div class="container">
      <div class="ml-3 mr-3">
        <h1>Foods List</h1>
      <AllFood />
        
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import AllFood from "@/components/AllFood.vue";

export default {
  name: "Foods",
  components: {
    Navbar,
    AllFood,
  },
};
</script>

<style></style>
