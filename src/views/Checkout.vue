<template>
  <div class="checkout">
      <Navbar />
      <div class="row justify-content-center">
        <div class="col text-center mt-4">
          <img src="../assets/img/checkout.svg" width="300">
          <h1><strong>Sukses!</strong></h1>
          <p>Pesanan segera di proses</p>
        </div>
      </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
export default {
  name: "Checkout",
  components: {
    Navbar
  }
}
</script>

<style>

</style>