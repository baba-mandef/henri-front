<template>
  <section class="section">
      <About></About>
      <WorkCard></WorkCard>
      <BlogCard></BlogCard>
      <Contact></Contact>
      
  
  </section>
</template>


<script>
import Card from "~/components/Card.vue";
import CardB from "~/components/CardB.vue";
import BlogCard from "~/components/BlogCard.vue";
import WorkCard from "~/components/WorkCard.vue";
import About from "~/components/About.vue";
import Contact from "~/components/Contact.vue";
export default {
  components: { Card, CardB, BlogCard, WorkCard, About, Contact },
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
