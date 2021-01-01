<template>
  <div class="hero">
    <!-- desktop -->
      <div class="d-none d-md-block">
        <div class="d-flex flex-row mt-4 mb-4">
          <div class="col-md-6 d-flex align-items-center">
            <div>
              <h2>
                <strong>Delicious Foods Menu,</strong> <br />
                in your gadget
              </h2>
              <p>Ayo pilih makanan favorit anda, dan pesanlah sekarang</p>
              <router-link class="btn btn-lg btn-success" to="/foods">
                Pesan <b-icon-arrow-bar-right></b-icon-arrow-bar-right>
              </router-link>
            </div>
          </div>
          <div class="col-md-6 d-flex align-items-center">
            <img src="../assets/img/hero.svg" width="100%" />
          </div>
        </div>
      </div>

      <!-- mobile -->
      <div class="d-sm-block d-md-none">
        <div class="row align-items-center mt-4">
          <div class="col-md-6 mb-4">
            <img src="../assets/img/hero.svg" width="100%" />
          </div>
          <div class="col-md-6">
            <div>
              <h2>
                <strong>Delicious Foods Menu,</strong> <br />
                in your gadget
              </h2>
              <p>Ayo pilih makanan favorit anda, dan pesanlah sekarang</p>
              <button class="btn btn-lg btn-success">
                Pesan <b-icon-arrow-bar-right></b-icon-arrow-bar-right>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
</template>
 
<script>
export default {
  name: "Hero",
};
</script>

<style></style>
