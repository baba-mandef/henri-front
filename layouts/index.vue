<template>
  <div>
    <div class="container">
      <navbar />
      <section class="hero is-medium">
        <div class="hero-body">
          <div class="is-hidden-tablet" style="padding-bottom:30px; margin:auto">
              
                <img  class="bannerimg" src="~/assets/images/ban.png" alt="">
              </div>
          <div class="columns">
            
            <div class="column is-half-tablet">
              <div>
                <h1
                  class="
                    title
                    is-size-2
                    is-size-3-mobile
                    is-size-3-touch
                    is-size-3-tablet
                    is-size-2-desktop
                    has-text-weight-bold has-text-centered-mobile has-text-primary
                  "
                >
                  We <span class="secolor">build</span> robust,<br />
                  scalable <span class="secolor">apps</span> to
                  <span class="secolor">solve</span> <br />
                  people everyday <span class="secolor">issues</span>.
                </h1>
                <br />
                <p
                  class="subtitle has-text-black has-text-centered-mobile "
                  id="message"
                >
                  <!--  <vue-typer
              
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
              ></vue-typer> -->
                  In a world where every day is a new challenge, we provide you
                  with digital solutions that make your life easier.
                </p>
                <div class="line"></div>
              </div>
            </div>
            <div class="column">
              <div class="is-hidden-mobile">
              
                <img  class="bannerimg" src="~/assets/images/ban.png" alt="">
              </div>
            </div>
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

.bannerimg {
 /*  background-image: url("~/assets/images/ban.jpeg");

  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;
  width: 500px;
  height: 250px;
  margin: auto; */
   position: relative; 
/* top: 0;
left: 0;
bottom: 0;
right: 0; */
box-sizing: border-box;
padding: 0;
border: none;
margin: auto;
display: block;

  

 
  top: 50%;
  
 


/* width: 0;
height: 0; */
/* min-width: 100%;
max-width: 100%;
min-height: 100%;
max-height: 100%; */
}
/* @media screen and (min-width: 1408px) {
  .bannerimg {
   border: solid 1px #2BABE2; 

    width: 500px;
     height: 250px;

    margin: auto;
    background-image: url("~/assets/images/ban.jpeg");

    background-repeat: no-repeat;
    background-size: contain;
    background-position: center;
  }
} */

.line {
 /*  width: 80%; */
  height: 10px;
  border: none;
  margin-top: 50px;
  border-radius: 10px;
  background-color: #393357;
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
  color: rgb(0, 0, 0);
}
.secolor{
  color: #BB9140
}
</style>
