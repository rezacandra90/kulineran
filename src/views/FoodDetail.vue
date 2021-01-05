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
          <img :src="'../img/' + product.gambar" class="img-fluid shadow" />
        </div>
        <div class="col-md-6">
          <h2>{{ product.nama }}</h2>
          <hr />
          <h4>
            Harga: <strong>RP. {{ product.harga }}</strong>
          </h4>
          <form class="mt-4" v-on:submit.prevent>
            <div class="form-group">
              <label for="">Jumlah</label>
              <input
                type="number"
                placeholder="jumlah"
                class="form-control"
                v-model="pesan.jumlah_pemesanan"
              />
            </div>
            <div class="form-group">
              <label for="">Keterangan</label>
              <textarea
                class="form-control"
                placeholder="Contoh: nasi setengah, pedes, tidak pedes,..."
                v-model="pesan.keterangan"
              ></textarea>
            </div>
          </form>
          <button class="btn btn-small btn-success" @click="pemesanan">
            <b-icon-cart></b-icon-cart> Pesan
          </button>
        </div>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Navbar from "../components/Navbar.vue";
import Footer from "../components/Footer.vue";
import axios from "axios";

export default {
  name: "FoodDetail",
  components: {
    Navbar,
    Footer,
  },
  data() {
    return {
      product: {},
      pesan: {},
    };
  },
  methods: {
    setProduct(data) {
      this.product = data;
    },
    pemesanan() {
      if (this.pesan.jumlah_pemesanan) {
        this.pesan.products = this.product;
        axios
          .post("http://localhost:3000/keranjangs", this.pesan)
          .then(() => {
            this.$router.push({
              path: "/keranjang"
            })
            this.$toast.success("berhasil masuk ke keranjang", {
              type: "success",
              position: "top",
              duration: 3000,
              dismissible: true,
            });
          })
          .catch((error) => console.log(error));
      } else {
        this.$toast
          .error("jumlah pemesanan harus diisi", {
            type: "error",
            position: "top",
            duration: 3000,
            dismissible: true,
          })
          .catch((error) => console.log(error));
      }
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/products/" + this.$route.params.id)
      .then((response) => this.setProduct(response.data))
      .catch((error) => console.log(error));
  },
};
Navbar;
</script>

<style></style>
