<template>
  <section class="section">

        <div class="columns">
          <div class="column has-text-centered hero1">
            <img src="~/assets/images/pannel.gif" alt="">
            <h2 class="title is-2 has-text-primary">We Are Under Maintenance</h2>
            <p class="subtitle is-4">We will be back soon !</p>
          </div>
        </div>

  </section>
</template>


<script>

export default {
  
  name: "Home",
  data() {
    return {
      rounded: false,
    };
  },

  layout: "index",
};
</script>

<style>
.hero-img {
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}
.hero1 {
  max-width: fit-content;
  margin: auto;
}
.center {
  margin: 0;

  position: absolute;
  top: 50%;
  left: 50%;
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}
</style>
