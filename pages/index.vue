<template>
  <section class="section">
   <div class="container is-max-desktop">
     <Services></Services>
    <Solutions></Solutions>
   <Team></Team>
    <Contact></Contact>
   </div>
  </section>
</template>


<script>

import Solutions from "~/components/Solutions.vue";
import Services from "~/components/Services.vue";
import Team from "~/components/Team.vue";
import Contact from "~/components/Contact.vue";
export default {
  components: { Solutions, Services, Team, Contact },
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
  height: 590px;
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
