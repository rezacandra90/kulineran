<template>
  <div class="BestFoods">
    <div class="input-group mb-3">
      <input
        v-model="search"
        type="text"
        class="form-control"
        placeholder="search foods"
        aria-label="Recipient's username"
        aria-describedby="button-addon2"
        @keyup="searchFood"
      />
      <button class="btn btn-success" type="button" id="button-addon2">
        <b-icon-search></b-icon-search>
      </button>
    </div>
    <div class="row mb-4">
      <div class="col-md-4" v-for="product in products" :key="product.id">
        <div class="card shadow mb-4">
          <img :src="'../img/' + product.gambar" class="card-img-top" />
          <div class="card-body">
            <h5 class="card-title">{{ product.nama }}</h5>
            <p class="card-text">Harga: Rp. {{ product.harga }}</p>
            <router-link :to="'/foods/'+product.id" class="btn btn-success"
              ><b-icon-cart></b-icon-cart> pesan</router-link
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "AllFood",
  data() {
    return {
      products: [],
      search: "",
    };
  },

  methods: {
    setProducts(data) {
      this.products = data;
    },
    searchFood() {
      axios
        .get("http://localhost:3000/products?q=" + this.search)
        .then((response) => this.setProducts(response.data))
        .catch((error) => console.log(error));
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/products")
      .then((response) => this.setProducts(response.data))
      .catch((error) => console.log(error));
  },
};
</script>

<style>
</style>