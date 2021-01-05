<template>
  <div class="Keranjang">
    <Navbar />
    <div>Keranjang</div>
    <Footer />
  </div>
</template>

<script>
import Navbar from "../components/Navbar.vue";
import Footer from "../components/Footer.vue";

export default {
  name: "Keranjang",
  components: {
    Navbar,
    Footer,
  },
};
</script>

<style>
</style>