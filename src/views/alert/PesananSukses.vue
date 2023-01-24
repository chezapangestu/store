<template lang="">
    <div class="pesanan-sukses">
    <NavbarComp />
    <div class="container">
      <div class="row justify-content-center mt-5">
        <div class="col text-center">
          <img src="../../../public/assets/images/waiting.svg" width="300" />
          <h2><strong>Sukses!!</strong></h2>
          <h4>Pesanan Anda segera diproses <br> Selamat Menunggu</h4>
        </div>
      </div>
    </div>
  </div>
</template>
<script>

import NavbarComp from '@/components/NavbarComp.vue'

export default {
  name: "PesananSukses",
  components: {
    NavbarComp,
  },
}
</script>
<style lang="">
    
</style>