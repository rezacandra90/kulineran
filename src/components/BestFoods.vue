<template>
  <div class="BestFoods">
    <div class="row mx-auto mb-4">
      <div class="col-md-4" v-for="product in products" :key="product.id">
        <div class="card shadow">
        <img :src="'../img/'+product.gambar" class="card-img-top">
        <div class="card-body">
            <h5 class="card-title">{{ product.nama }}</h5>
            <p class="card-text">Harga: Rp. {{ product.harga }}</p>
            <router-link :to="'/foods/'+product.id" class="btn btn-success"><b-icon-cart></b-icon-cart> pesan</router-link>
        </div>
        </div>
        
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "BestFoods",
  data() {
    return {
      products: [],
    };
  },
  methods: {
    setProducts(data) {
      this.products = data;
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/best-products")
      .then((response) => this.setProducts(response.data))
      .catch((error) => console.log(error));
  },
};
</script>

<style>
</style>