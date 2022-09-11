<template>
  <section class="section">
    <div class=" container1">
      <div class=" vertical-center has-text-centered ">
        <img src="~/assets/images/pannel.gif" alt="" />
        <div>
          <img
            width="90px"
            src="~/assets/henri-dev-circle.png"
            alt="{Henri-dev}"
          />
        </div>
      <h2 class="title is-2 has-text-primary">We Are Under Maintenance</h2>
        <p class="subtitle has-text-weight-semibold has-text-black is-4">
          We will be back soon !
        </p>
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

/* .hero1 {
  max-width: fit-content;
  margin: auto;
} */
.vertical-center {
  width: fit-content;
  margin: 0;
  position: absolute;
  top: 50%;
  left: 50%;
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}
.container1 {
  height: 500px;
  position: relative;

}
</style>
