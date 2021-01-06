<template>
  <div class="home">
      <Navbar />
    
      <Hero />

      <div class="row mx-auto mb-4">
        <div class="col">
          <h2>Best Foods</h2>
        </div>
        <div class="col">
          <router-link to="/foods" class="btn btn-sm btn-success float-right"
            ><b-icon-eye></b-icon-eye> view all</router-link
          >
        </div>
      </div>

      <BestFoods/>

    <div class="mt-4 mb-4" style="height: 50px">
      <hr>
    </div>
    <Footer/>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import Hero from "@/components/Hero.vue";
import BestFoods from "@/components/BestFoods.vue";
import Footer from "@/components/Footer.vue";


export default {
  name: "Home",
  components: {
    Navbar,
    Hero,
    BestFoods,
    Footer,
  },

};
</script>
