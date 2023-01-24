<template>
  <div class="home">
    <NavbarComp />
    <div class="container">
      <HeroComp />

      <div class="row mt-4">
        <div class="col text-left">
          <h2>
            Best
            <strong>Foods</strong>
          </h2>
        </div>
        <div class="col">
          <router-link to="/foods" class="btn btn-red float-right">
            <b-icon-eye></b-icon-eye>Lihat Semua
          </router-link>
        </div>
      </div>

      <div class="row mb-4">
        <div class="col-md-4 mt-4"  v-for="product in products" :key="product.id">
          <CardProductComp :product="product"/>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import NavbarComp from '@/components/NavbarComp.vue'
import HeroComp from '@/components/HeroComp.vue'
import CardProductComp from '@/components/CardProductComp.vue'
import axios from "axios";

export default {
  name: 'HomeView',
  components: {
    NavbarComp,
    HeroComp,
    CardProductComp
  },
  data() {
    return {
      products: [],
    };
  },
  methods:{
    setProducts(data){
      this.products = data;
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/best-products")
      .then((response) => this.setProducts(response.data))
      .catch((error) => console.log(error))
  },
};
</script>
