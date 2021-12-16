<template>
  <div>
    <div class="banner">
      <navbar />
      <section class="hero1">
        <div class="hero-body">
          <div class="center">
            <h1
              class="
                title
                is-size-1 is-size-4-mobile is-size-2-tablet is-size-1-desktop,
                has-text-centered has-text-white
              "
            >
              <span style="color: lightblue">{ </span> PROJETS
              <span style="color: lightblue">}</span>
            </h1>
            <br />
            <p class="subtitle has-text-centered sub" id="message">
              <vue-typer
                :text="[
                  '{ Imagination, beyond comprehension ! }',
                  '{ Let IT change your life ! }',
                ]"
                :repeat="3"
                :shuffle="false"
                initial-action="typing"
                :pre-type-delay="70"
                :type-delay="90"
                :pre-erase-delay="500"
                :erase-delay="100"
                erase-style="backspace"
                :erase-on-complete="false"
                caret-animation="blink"
              ></vue-typer>
            </p>
          </div>
        </div>
      </section>
    </div>
    <nuxt />
    <Footer />
  </div>
</template>

<script>
import navbar from "./partials/navbar.vue";
import Footer from "./partials/Footer.vue";
import { VueTyper } from "vue-typer";

export default {
  components: { navbar, Footer, VueTyper },
};
</script>

<style>
.banner {
  background-image: url("~/assets/images/1.jpg");

  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}

.center {
  margin: 0;

  position: absolute;
  top: 50%;
  left: 50%;
  -ms-transform: translate(-50%);
  transform: translate(-50%);
}
.vue-typer .custom.char {
  color: white;
}
</style>
