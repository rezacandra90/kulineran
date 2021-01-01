<template>
  <div class="FoodDetail">
    <Navbar />
    <div class="container">
      <!-- Breadcrumb -->
      <div class="row mt-4">
        <div class="col">
          <nav aria-label="breadcrumb">
            <ol class="breadcrumb">
              <li class="breadcrumb-item">
                <router-link to="/" class="text-dark">Home</router-link>
              </li>
              <li class="breadcrumb-item">
                <router-link to="/foods" class="text-dark">Foods</router-link>
              </li>
              <li class="breadcrumb-item active" aria-current="page">
                Food Detail
              </li>
            </ol>
          </nav>
        </div>
      </div>

      <div class="row mx-auto">
        <div class="col-md-6">
            <img :src="'../img/'+product.gambar" class="img-fluid shadow">
        </div>
        <div class="col-md-6">
            <h2>{{product.nama}}</h2>
            <hr>
            <h4>Harga: <strong>RP. {{product.harga}}</strong></h4>
            <div class="mt-4">
                <div class="form-group">
                <label for="">Jumlah</label>
                <input type="number" placeholder="jumlah" class="form-control">
            </div>
            <div class="form-group">
                <label for="">Keterangan</label>
                <textarea class="form-control"  placeholder="Contoh: nasi setengah, pedes, tidak pedes,..."></textarea>
            </div>
            </div>
            <button class="btn btn-small btn-success"><b-icon-cart></b-icon-cart> Pesan</button>
        </div>
        
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Navbar from "../components/Navbar.vue";
import Footer from "../components/Footer.vue";
import axios from "axios"

export default {
  name: "FoodDetail",
  components: {
    Navbar,
    Footer,
  },
  data() {
    return {
      product: {},
    };
  },
  methods: {
    setProduct(data) {
      this.product = data;
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/products/"+this.$route.params.id)
      .then((response) => this.setProduct(response.data))
      .catch((error) => console.log(error));
  },
};
Navbar;
</script>

<style>
</style>