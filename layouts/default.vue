<template>
  <div>
    <navbar />
    <nuxt />
    <Footer />
  </div>
</template>

<script>
import navbar from "./partials/navbar.vue";
import Footer from "./partials/Footer.vue";

export default {
  components: { navbar, Footer },

  

};
</script>
